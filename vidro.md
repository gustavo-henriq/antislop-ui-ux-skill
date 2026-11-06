# Vidro sem cara de IA

Glassmorphism não é proibido. O que dá cara de IA é o **vidro decorativo**: blur leitoso sobre gradiente liso, borda branca e glow, repetido em card de conteúdo. Vidro de verdade é uma **camada com função** que deixa ver o que está atrás — e, quando dá, deforma esse fundo nas bordas.

## Diagnóstico rápido

| Vidro de IA | Vidro real |
|---|---|
| Fundo liso ou gradiente sem nada para mostrar | Foto, mapa, cor viva ou conteúdo rolando atrás |
| Branco leitoso, quase opaco | Transparência que preserva forma e cor |
| `blur(24px)` + borda branca + glow | `blur` médio + `saturate`, luz na borda de cima, sombra embaixo |
| Vidro em card, formulário, tabela | Vidro só em camada flutuante: nav, sheet, modal, HUD |
| Vários vidros empilhados | Uma camada de vidro por tela |
| Texto sem contraste | Texto legível no pior ponto do fundo |
| Sem fallback | Fallback sólido quando não há suporte |

## Onde é legítimo

- **Barra de navegação flutuante** sobre conteúdo que rola.
- **Bottom sheet / modal / popover** sobre a tela que continua visível.
- **HUD ou controle sobre mídia** (player, mapa, câmera).
- **Header sticky** que precisa mostrar que o conteúdo passa por baixo.
- **Uma peça de destaque** em que o vidro é o assunto (um card de hero, uma lente).

Se o fundo atrás é chapado, o vidro não tem o que mostrar. Nesse caso, superfície sólida.

## Regras

1. **Só onde há camada.** Vidro existe para separar planos. Se não há plano atrás, é textura — e textura de vidro é enfeite.
2. **O fundo precisa valer a pena.** Formas, cor, foto ou movimento. Vidro sobre `linear-gradient` liso é o padrão de IA.
3. **Um vidro por tela.** No máximo um sistema (nav + sheet podem compartilhar a mesma receita). Vidro sobre vidro vira gelatina.
4. **Legibilidade primeiro.** Contraste AA no pior ponto do fundo. Se não passar, aumente a opacidade ou ponha um scrim local atrás do texto.
5. **Vidro não é conteúdo primário.** Formulário, tabela e texto de leitura ficam em superfície sólida.
6. **Luz coerente.** Highlight claro na borda de cima, sombra escura embaixo. Glow para fora não é luz, é slop.
7. **Performance.** `backdrop-filter` é caro: área pequena, sem animar o blur, fallback sólido.
8. **Movimento curto.** Entrada/saída de 160–240 ms; respeite `prefers-reduced-motion`.

## Receita A — vidro contido (CSS puro)

O jeito confiável: blur + saturação + transparência em camadas + luz de borda. Não deforma, mas lê como vidro.

```css
.vidro {
  --vidro-blur: 14px;
  position: relative;
  background: linear-gradient(180deg, rgba(255,255,255,.16), rgba(255,255,255,.05));
  -webkit-backdrop-filter: blur(var(--vidro-blur)) saturate(165%);
  backdrop-filter: blur(var(--vidro-blur)) saturate(165%);
  border: 1px solid rgba(255,255,255,.22);
  box-shadow:
    inset 0 1px 0 rgba(255,255,255,.38),   /* luz de cima */
    inset 0 -1px 0 rgba(0,0,0,.28),        /* sombra de baixo */
    0 12px 32px rgba(0,0,0,.28);           /* profundidade real */
  color: #fff;
  text-shadow: 0 1px 2px rgba(0,0,0,.45);
}

/* brilho de quina, não glow */
.vidro::after {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: inherit;
  pointer-events: none;
  background: linear-gradient(135deg, rgba(255,255,255,.18), transparent 42%);
  mix-blend-mode: screen;
}

/* fallback: sem suporte, o vidro vira superfície sólida */
@supports not ((backdrop-filter: blur(1px)) or (-webkit-backdrop-filter: blur(1px))) {
  .vidro { background: rgba(18, 20, 24, .94); }
}
```

Para fundo claro, inverta: `rgba(0,0,0,.10)` a `rgba(0,0,0,.04)`, borda `rgba(255,255,255,.55)`, texto escuro.

## Receita B — refração de verdade

`backdrop-filter` só **desfoca**; não entorta. Para o fundo parecer visto através de uma lente, você precisa de uma **cópia do fundo** dentro do vidro, ampliada, desfocada e deslocada — a borda mostra a distorção.

```html
<div class="lente">
  <div class="lente__fundo" aria-hidden="true"></div>
  <div class="lente__conteudo">…</div>
</div>
```

```css
.lente {
  position: relative;
  overflow: hidden;
  border-radius: 20px;
  isolation: isolate;
}

.lente__fundo {
  position: absolute;
  inset: -6%;
  background-image: url("fundo.jpg");
  background-size: cover;
  background-position: center;
  background-attachment: fixed; /* alinha com um fundo fixo da página */
  filter: blur(9px) saturate(150%);
  transform: scale(1.05);       /* a borda "entorta" o que está atrás */
  z-index: -1;
}

.lente__conteudo {
  position: relative;
  padding: 20px;
  color: #fff;
  text-shadow: 0 1px 2px rgba(0,0,0,.5);
}
```

O `background-attachment: fixed` só alinha se o fundo da página também for fixo. Se a seção tiver imagem própria, use a mesma imagem e a mesma posição nos dois — é o caso mais controlável.

Para a borda deformar de fato, aplique um filtro SVG na cópia do fundo (não no `backdrop-filter`, que tem suporte irregular):

```html
<svg width="0" height="0" aria-hidden="true">
  <filter id="refract">
    <feTurbulence type="fractalNoise" baseFrequency="0.006 0.01" numOctaves="2" seed="7" result="n"/>
    <feDisplacementMap in="SourceGraphic" in2="n" scale="14"
      xChannelSelector="R" yChannelSelector="G"/>
  </filter>
</svg>
```

```css
.lente__fundo { filter: blur(7px) saturate(150%) url(#refract); }
```

Use `scale` baixo (10–18) e blur por cima: a distorção aparece na borda sem desalinhar o miolo. É caro — reserve para uma peça, não para a tela inteira. Refração em tempo real de verdade (lente sobre vídeo, por exemplo) pede WebGL; só vale quando o vidro é o produto.

## Checklist

- [ ] O que está atrás do vidro? Se não há nada, use sólido.
- [ ] O texto passa AA no pior ponto do fundo?
- [ ] A luz vem de cima (highlight em cima, sombra embaixo)?
- [ ] É a única camada de vidro da tela?
- [ ] O vidro tem função (separar planos) ou só enfeite?
- [ ] Existe fallback sólido?
- [ ] A área é pequena o bastante para o `backdrop-filter` não pesar?

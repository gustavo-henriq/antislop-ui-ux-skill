# Estética de IA — checklist

Checklist visual do que dá "cara de IA". Para cada item: **o sinal**, o **CSS de assinatura**, a **correção** e **quando é legítimo**. A versão visual (pares slop → correção) está em `anti-slop/galeria.html`; o catálogo completo (com mais sinais, em categorias) está em `anti-slop/catalogo.md`.

Passe por esta lista **em toda tela**, tanto na que existe quanto na que você acabou de implementar.

---

## 1. Degradê em tudo

- **Sinal:** fundos, botões, textos e até bordas em gradiente, cada um com um degradê diferente.
- **CSS de assinatura:** `background: linear-gradient(...)` espalhado em vários elementos; `background-clip: text` com gradiente.
- **Correção:** cor sólida como base; **um** degradê no máximo, e só onde conta algo (uma transição de estado, uma profundidade real).
- **Legítimo quando:** o gradiente codifica uma mudança de dado (ex.: nível que vai de "ok" a "atenção") ou é tonal, na mesma cor, para dar volume (ver *Acabamento* no SKILL.md).

## 2. Glow em tudo (não o glow em si)

- **Sinal:** brilho suave espalhado por botões, cards, avatares e texto — o "aura" sem fonte de luz, na tela toda.
- **CSS de assinatura:** `box-shadow: 0 0 24px rgba(<cor>, .4)` em vários elementos; `filter: drop-shadow(0 0 8px ...)`.
- **Correção:** glow em **um ponto só** (a luz que importa), com fonte de luz clara; no resto, contorno fino ou sombra curta realista. O problema é o "em tudo", não o glow.
- **Legítimo quando:** o elemento emite luz de verdade (LED, sol, alerta) ou o glow é o ponto focal de um efeito temático (uma estrela, um cometa). Um glow bem posto passa; três é slop.

## 3. Vidro fumê (glassmorphism) sem função

- **Sinal:** `backdrop-filter: blur()` em cards, modais e barras, sem função — só pra parecer "moderno".
- **CSS de assinatura:** `background: rgba(255,255,255,.1); backdrop-filter: blur(20px)` sobre fundo liso, com borda branca e glow.
- **Correção:** vidro só quando há conteúdo atrás e a camada tem função (nav flutuante, sheet, modal, HUD). Se o fundo é chapado, use sólido. Vidro real = blur + saturação + luz de borda + transparência que deixa ver o fundo; receita e limites em `vidro.md`.
- **Legítimo quando:** há conteúdo real rolando por trás, a camada separa planos e o texto continua legível no pior fundo. Vidro decorativo sobre gradiente é slop; vidro com refração e conteúdo visível é ofício.

## 4. Sombra e raio iguais em tudo

- **Sinal:** todos os cards com o mesmo raio (16 px) e a mesma sombra longa, dando um visual "gerado em série".
- **CSS de assinatura:** um único valor de `border-radius` e `box-shadow` copiado em todo componente.
- **Correção:** raios em escala (o de dentro = o de fora menos o espaçamento); sombra só no que flutua sobre outra superfície.
- **Legítimo quando:** é uma família de componentes que de fato compartilham a mesma superfície.

## 5. Ícones em quadrado tingido

- **Sinal:** todo ícone dentro de um quadradinho arredondado com fundo colorido — o "chip" que não agrupa nada.
- **CSS de assinatura:** `.icon { width:40px; height:40px; border-radius:10px; background:<cor>; }`.
- **Correção:** ícone solto, na cor do texto; o contêiner só quando o ícone é a identidade de um item (ex.: avatar, logo).
- **Legítimo quando:** o quadrado é a "cara" do item (um logo de marca, um avatar).

## 6. Pílulas sem significado

- **Sinal:** chips/pills coloridos que etiquetam coisas óbvias ou não fazem nada ("agrupar", "novo", "online").
- **CSS de assinatura:** `border-radius: 999px` com fundo colorido em rótulos que não são estado.
- **Correção:** pílula só quando carrega um estado real (um status, um filtro ativo); senão, texto simples.
- **Legítimo quando:** a pílula é um estado clicável (filtro selecionado) ou um selo de dado (uma categoria).

## 7. Tudo centralizado

- **Sinal:** títulos, parágrafos e botões centralizados "por padrão", sem decisão de alinhamento.
- **CSS de assinatura:** `text-align: center` em tudo, inclusive em listas e parágrafos longos.
- **Correção:** alinhar à esquerda para leitura; centralizar só o herói ou um estado vazio curto.
- **Legítimo quando:** é um estado vazio, um título de herói de uma linha, um diálogo.

## 8. Gráficos decorados

- **Sinal:** gráfico de pizza/donut/linha com gradiente, sombra e legenda para um dado que cabia numa frase ou num número.
- **CSS de assinatura:** SVG com gradientes + `drop-shadow` + animação de "contar".
- **Correção:** se o dado é uma frase, escreva a frase. Se é um número, mostre o número. Gráfico só quando há comparação/evolução a mostrar.
- **Legítimo quando:** há mais de uma série a comparar e a forma revela a relação.

## 9. Fade-up em tudo / shimmer em loop

- **Sinal:** toda seção entra com fade+deslizar ao scroll; brilho pulsando em placeholder; shimmer em degradê que nunca para.
- **CSS de assinatura:** `animation` de fade-up em todos os blocos; `@keyframes` de shimmer com `background-position` infinito.
- **Correção:** movimento com causa (ver *Movimento* no SKILL.md). Sem movimento de abertura; shimmer só em carregamento real.
- **Legítimo quando:** o shimmer representa um carregamento de verdade; o fade marca uma troca de estado.

## 10. Blobs de cor por blur

- **Sinal:** manchas coloridas desfocadas ao fundo pra "encher" a tela.
- **CSS de assinatura:** `filter: blur(80px)` em círculos coloridos posicionados atrás do conteúdo.
- **Correção:** fundo liso (a cor de canvas do projeto). Se precisar de atmosfera, use textura sutil, não blob.
- **Legítimo quando:** o blob é uma luz/ambiente real e reproduzível no produto.

## 11. Espelhado de layout (tudo igual em todo lugar)

- **Sinal:** seções com a mesma estrutura de card repetida ("3 cards + botão", "hero + 3 colunas"), sem variação de ritmo.
- **CSS de assinatura:** o mesmo grid copiado em seção após seção.
- **Correção:** variar o ritmo (uma seção larga, uma com duas colunas, uma lista); a repetição é o slop.
- **Legítimo quando:** é uma lista/grid de dados homogêneos de verdade.

## 12. Confete / enfeite sem causa

- **Sinal:** confete, partículas, parallax e brilhos decorativos que não respondem a nada.
- **Correção:** remover. Enfeite entra só se responde a uma ação ou estado (comemoração de uma meta real).
- **Legítimo quando:** há um evento real a celebrar.

---

## Como usar o checklist

1. Passe item a item na tela (antiga ou nova), pulando o que estiver em *Exceções ao checklist* no `gosto.md` do projeto.
2. Para cada sinal encontrado, aponte **no lugar** onde ele aparece.
3. Corrija ou justifique (alguns são legítimos no contexto).
4. Confira de novo na **segunda checagem** — o próprio desenho novo também entra slop.

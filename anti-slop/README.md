# Acervo anti-slop

Exemplos **explícitos** do que dá cara de IA, em texto, pares visuais e prints reais (`referencias/`). Use como régua na *Auditoria* e na *segunda checagem*.

Três arquivos aqui:

- **`catalogo.md`** — o catálogo completo (80 padrões em categorias, com fontes). É a referência principal.
- **`galeria.html`** — versão visual, self-contained, com 20 pares **slop → correção** lado a lado. Abra no navegador e tire prints.
- **Este README** — o resumo em tabela dos 12 sinais principais.

O checklist rápido de estética está em `estetica-ia.md`; o catálogo completo em `catalogo.md`.

## Catálogo

| # | Sinal | O que denuncia | Correção |
|---|-------|----------------|----------|
| 1 | Degradê em tudo | `linear-gradient` em fundo, botão, texto e borda | cor sólida; 1 degradê no máx., só onde conta |
| 2 | Halo / glow | `box-shadow: 0 0 24px rgba(...)` sem fonte de luz | contorno fino ou sombra curta real |
| 3 | Vidro fumê | `backdrop-filter: blur()` sem função | superfície sólida; blur só em véu útil |
| 4 | Sombra/raio iguais | mesmo raio e sombra copiados em tudo | raios em escala; sombra só no que flutua |
| 5 | Ícone em quadrado | `.icon { w40 h40 r10 bg:cor }` | ícone solto na cor do texto |
| 6 | Pílula sem função | `border-radius:999px` em rótulo que não é estado | texto simples; pílula só pra estado real |
| 7 | Tudo centralizado | `text-align:center` em listas/parágrafos | esquerda pra leitura; centro só no herói/vazio |
| 8 | Gráfico decorado | donut+gradiente pra um número | frase ou número; gráfico só com série a comparar |
| 9 | Fade-up/shimmer | `animation` de fade em tudo; shimmer infinito | movimento com causa; shimmer só em loading real |
| 10 | Blob por blur | `filter:blur(80px)` em mancha colorida | fundo liso; atmosfera com textura, não blob |
| 11 | Layout espelhado | mesmo grid copiado seção a seção | variar o ritmo |
| 12 | Confete/enfeite | partículas/parallax sem responder a nada | remover; enfeite só com evento real |

## Como adicionar seus próprios prints

Coloque a imagem aqui com o padrão `NN-<sinal>.png` (ex.: `01-degrade.png`) e, se for um par, `NN-<sinal>-antes.png` / `NN-<sinal>-depois.png`. Adicione a linha correspondente na tabela acima.

> Dica: os próprios prints dos reviews dos seus apps são os melhores exemplos — são reais, não genéricos.

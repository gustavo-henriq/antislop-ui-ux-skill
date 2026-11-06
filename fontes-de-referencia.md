# Fontes de referência (curadas)

Use estas fontes quando o usuário pedir inspiração (ver *Buscar inspiração* no SKILL.md). Pesquise **apenas aqui** para o tipo de tela; busca aberta devolve muito slop.

> **Como acessar:** quem navega é um **subagente no modelo mais barato**, que abre as fontes e tira **print** (não baixa a página). A IA principal só decide o que buscar e analisa os prints que voltarem. A quantidade segue a meta de cada modo (ver *Modo barato × modo guiado* no SKILL.md).

> Regra de ouro: toda referência vira **conceito** (hierarquia, ritmo, metáfora), nunca **cópia** (paleta, fonte, layout literal). Depois de escolher, filtre o exemplo pelo checklist de `estetica-ia.md` — referência boa também vem contaminada.

> **Fonte por plataforma:** para app de celular, comece por *Fluxos e apps*. *Web e visual* e *Landing / SaaS* só entram em busca de site ou landing page, ou quando o usuário pedir. *Movimento* e *Componentes* valem para as duas, conferindo a plataforma de cada exemplo. *Identidade e sistemas visuais* vale para qualquer plataforma, mas só para identidade: nunca para estrutura de tela.

## Fluxos e apps (mobile/produto)

- **Mobbin** — mobbin.com — fluxos reais de apps, organizados por padrão de tela. Novidades: mobbin.com/discover/apps/ios/latest (o que está saindo agora; use o fluxo, não a tela solta).
- **Pageflows** — pageflows.com — fluxos de onboarding/upsell passo a passo.
- **Refero** — refero.design — padrões de interface por categoria, direto ao ponto.
- **Appshots** — appshots.design — biblioteca de fluxos e telas. **Use o site em si como referência** (como organiza, navega e apresenta os fluxos), não os elementos/screenshots de dentro dele como peças a copiar.
- **ScreensDesign** — screensdesign.com — gravações completas de onboarding → paywall → pós-compra, com receita estimada. Use para a **sequência** e para entender o que converte; nunca copie a tela.
- **Appkittie** — appkittie.com — inteligência de mercado (receita, downloads, anúncios) com biblioteca de onboardings e paywalls. Use para decidir **o que vale a pena** e ver o fluxo que já converte; a referência visual continua sendo a identidade do projeto.

## Movimento e microinteração

- **60fps** — 60fps.design — detalhes de animação e interação de apps reais, filtráveis por gesto (drag, swipe, long press), efeito (morph, spring, stagger) e elemento (bottom sheet, tab bar, toast). Use para timing, easing e ideia de transição — não para copiar o movimento inteiro.

## Identidade e sistemas visuais

Use em *Chegar cru* e em buscas de paleta, tipografia e superfície, quando o usuário pedir referências.

- **GradientDeck UI** — ui.gradientdeck.com — 1.286 arquivos `DESIGN.md` escritos a partir de sites reais, gratuitos e sem login. Cada um traz cores, tipografia, espaçamento, componentes e regras de uso.
  - **Como buscar:** filtre `https://ui.gradientdeck.com/library.json` por setor, tema, cores e fontes. Depois abra de 3 a 5 estilos em `https://ui.gradientdeck.com/styles/{slug}/design.md`. É texto, então leia o arquivo em vez de tirar print.
  - **Aproveitar:** proporção de cor, hierarquia de tipos e regra de superfície. Antes de perguntar, aplique cada conceito num pedaço real da tela, com cores e fontes próprias do projeto. Conceito não significa só texto.
  - **Não fazer:** nunca salve um desses arquivos como `DESIGN.md` ou `receitas.md` do projeto, nem copie cores, fontes ou layout literais. Os designs pertencem aos sites de origem. Fonte paga só com licença.
  - **Limite:** são sites, não apps. Não serve para estrutura de tela de celular.

## Web e visual

- **Awwwards** — awwwards.com — sites com direção de arte forte (cuidado: tende ao "premiado exagerado"; filtre).
- **Godly** — godly.website — sites com estética cuidada e curada.
- **Land-book** — land-book.com — landing pages variadas.
- **Minimal Gallery** — minimal.gallery — referência de minimalismo real (bom contraponto ao slop).
- **Dark Mode Design** — darkmodedesign.com — telas escuras bem resolvidas (útil quando o produto é escuro primeiro).
- **Kombai Selects** — kombai.com/selects/ — curadoria de X, Dribbble e Behance, com interfaces que dá para remixar. Útil para web, landing e dashboard; **cuidado:** Dribbble e Behance tendem ao mockup bonito e irreal — aproveite a ideia, não o pixel.

## Landing / SaaS

- **SaaS Landing Page** — saaslandingpage.com — landings de SaaS.
- **Layers** — layers.to — componentes e interações isolados.

## Componentes e padrões de produto

Para telas de app (dashboard, painel, chat, tabela), a referência é de **anatomia**, não de estética. O guia de como montar cada peça está em `componentes.md`.

- **BoardUI** — boardui.com/pt-br — sistema de design React (103 componentes, 19 gráficos, 400+ tokens) para dashboards e interfaces de agentes. A melhor referência para app de produto: tabela de dados (busca → filtro → status → ações), tiles de métrica com comparação, cards de gráfico com seletor de período, estados de agente (composer, progresso, fontes), upload com validação, calendário, sidebar.
  - **Aproveitar:** hierarquia de dados, densidade de tabela, estados explícitos (vazio/carregando/erro), tokens em vez de valores soltos, agrupamento por seção.
  - **Descartar:** o look default "shadcn/SaaS" (cinza-neutro + Inter + cantos iguais), pílulas de status decorativas, gradiente em gráfico, widgets de streak/anel quando não são o produto.
- **Layers** — layers.to — componentes isolados; bom para conferir estado e microinteração de uma peça só.

## Como registrar uma referência

Ao salvar um print em `inspiracao/`, anote no README da pasta:

```
[NN]-<nome>.png — o que resolve bem: <1 frase>. O que aproveitar: <1 frase concreta>.
```

Não cole a imagem sem anotação: referência sem "o que aproveitar" vira cópia.

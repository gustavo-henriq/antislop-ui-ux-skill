# Catálogo completo de anti-slop

Padrões a reconhecer, com o que são e como corrigir. Complementa o checklist rápido de `estetica-ia.md` e a galeria visual `galeria.html`.

> Fonte dos padrões: [impeccable.style/slop](https://impeccable.style/slop) (Impeccable, de Paul Bakaus) — adaptado e traduzido para o PT-BR e para a voz desta skill.

Duas marcas:

- **AI slop** — hábitos visuais típicos de modelos de IA.
- **Qualidade** — problemas que tornam a interface mais difícil de usar.

---

## 1. Seu design system

Padrões que checam a tela contra o próprio `DESIGN.md`/`receitas.md` do projeto.

### Fonte fora do design system *(Qualidade)*
A fonte usada não está no sistema tipográfico do projeto. Use uma aprovada, ou registre a adição se for intencional.

### Cor fora do design system *(Qualidade)*
A cor não está na paleta documentada. Use uma cor da paleta, ou adicione a nova ao sistema.

### Raio (border-radius) fora do design system *(Qualidade)*
O raio usado não está na escala documentada. Use um raio existente, ou atualize o sistema para incluir a forma nova.

### Tamanho de fonte fora do design system *(Qualidade)*
O tamanho não está na escala tipográfica. Use um passo existente, ou adicione um novo à escala.

---

## 2. Detalhes visuais

### Fundo de grade decorativo *(AI slop)*
Uma grade de linhas ao fundo só enfeita, sem ajudar a usar a página. Grade só para canvas, mapa ou tarefa que exige medição.

### Borda de destaque em elemento arredondado *(AI slop)*
Borda grossa colorida faz o contorno do card competir com o conteúdo. Use borda mais leve, ou deixe o fundo definir o card.

### Glassmorphism em todo lugar *(AI slop)*
Blur, card de vidro e borda brilhante usados como decoração, não para resolver camada de verdade. Vidro precisa de conteúdo atrás e função; se o fundo é chapado, use sólido. Vidro real (blur + saturação + luz de borda + refração) é permitido — receita em `vidro.md`.

### Borda lateral de destaque (side-tab) *(AI slop)*
Uma faixa colorida grossa na lateral faz um card comum parecer alerta. Remova quando não há status ou aviso a comunicar.

### Borda fina + sombra larga *(AI slop)*
Borda de 1px e sombra ampla definem o mesmo card. Escolha uma: a borda ou a sombra.

### Listras de gradiente repetidas *(AI slop)*
Listras repetidas preenchem espaço vazio com ruído. Use superfície lisa, ou textura que pertença ao design.

### Border-radius extremo em cards *(AI slop)*
Raio grande espreme o conteúdo e faz todo card parecer igual. Reduza a curva ao tamanho do card.

### Ilustrações SVG toscas *(AI slop)*
Mascote ou cena desenhada às pressas deixa a página com cara de inacabada. Use ilustração bem-feita ou foto — ou remova.

---

## 3. Tipografia

### Rótulo acima de um título *(AI slop)*
Um rótulo pequeno acima do título adiciona uma linha de leitura. Remova se repetir o título, ou funda as palavras úteis no próprio título.

### Texto de interface minúsculo *(Qualidade)*
Navegação, link e controle ficam difíceis de usar quando o texto é pequeno demais. Aumente para ler sem dar zoom.

### Uma palavra sozinha na última linha *(Qualidade)*
Parágrafo que termina numa palavra só deixa um vão na coluna. Reajuste com `text-wrap: pretty` ou mude a medida.

### Título com última linha "cotoco" *(Qualidade)*
Título de várias linhas cuja última linha é um toco parece inacabado. Use `text-wrap: balance` para equalizar.

### Hierarquia tipográfica achatada *(AI slop)*
Títulos e corpo parecidos demais dificultam escanear. Diferencie tamanho, peso ou espaçamento.

### Ícone em quadrado empilhado sobre o título *(AI slop)*
Ícone num quadrado arredondado acima do título é o card de feature clássico de IA. Ponha o ícone ao lado do título, ou remova o contêiner.

### Manchete em serifa itálica *(AI slop)*
Serifa itálica gigante é atalho pronto para "cara editorial". No *Perfil padrão*, evite serifa fora de produto editorial; a lista de escolhas por tier está em `tipografia.md`.

### Badge acima da manchete principal *(AI slop)*
Pílula acima da manchete parece clicável e compete com a mensagem. Remova se não agrega, ou leve a informação para o título.

### Título hero gigante *(AI slop)*
Manchete longa em tamanho display ocupa a primeira dobra sozinha. Encurte ou reduza para sobrar espaço para explicar e agir.

### Espaçamento de letras espremido *(AI slop)*
Letras coladas ficam difíceis de distinguir. Afrouxe até cada caractere ficar claro, sobretudo em telas pequenas.

### Fonte saturada (Inter/Geist em tudo) *(AI slop)*
Geist entrega IA na hora; Inter é saturada mas passa despercebida por lembrar a SF, a fonte de sistema da Apple — aceitável como neutra. Prefira fontes indie/menos conhecidas; a lista por tier está em `tipografia.md`.

### Uma fonte só para tudo *(AI slop)*
Uma família pode funcionar na página toda; se tudo parecer achatado, varie tamanho/peso/espaço antes de decidir por uma segunda família.

### Texto corrido em caixa alta *(Qualidade)*
Trechos longos em maiúsculas cansam. Use caixa de frase no corpo; maiúsculas só em rótulos ou títulos curtos.

---

## 4. Cor & contraste

### Halo de fundo em gradiente radial *(AI slop)*
Halo claro atrás do conteúdo é o fundo de IA clássico. Slop quando é a tela toda; um halo focal (uma luz, um céu) com propósito passa. Remova quando compete com o conteúdo ou não tem papel.

### Holofote suave atrás do conteúdo *(AI slop)*
Brilho atrás de uma seção dá ênfase sem explicar o que importa. Um holofote só, com sentido, é ok; vários viram slop. Use espaçamento, contraste ou um título claro.

### Paleta de cor de IA *(AI slop)*
Roxo em gradiente e ciano brilhante sobre fundo escuro são padrões de IA. Construa a paleta a partir da identidade do produto.

### Modo escuro com acentos brilhantes *(AI slop)*
Acentos com glow em tudo viram muro de neon. Um acento brilhante focal (a estrela, o destaque) é bem-vindo; o muro é que não. Reduza o brilho para a informação útil aparecer.

### Texto em gradiente *(AI slop)*
Gradiente muda a cor ao longo de um título ou número, só por decoração. Use uma cor sólida e dê ênfase com tamanho/peso.

### Texto cinza sobre fundo colorido *(Qualidade)*
Cinza neutro fica lavado sobre superfície colorida. Use tom mais escuro ou texto claro, e confira o contraste real.

### Paleta creme/bege *(AI slop)*
Creme e bege viram substituto preguiçoso de paleta. Mantenha quando pertencem ao produto e escolha o resto com o mesmo cuidado.

---

## 5. Layout & espaço

### Rótulos de seção numerados minúsculos *(AI slop)*
Números ao lado de títulos adicionam ruído quando não há sequência. Numeração só para passos ou ordem que importa.

### Cards encostados na borda do scroller *(Qualidade)*
Cards colados na borda sem respiro. Adicione espaço igual nas duas pontas para a primeira e a última terem limite claro.

### Texto coberto por outro elemento *(Qualidade)*
Uma camada opaca cobre texto legível. Mova a camada ou dê espaço claro ao texto.

### Colunas de abertura desbalanceadas *(Qualidade)*
Uma coluna desce muito além da outra, deixando vão. Reequilibre, ou mova a seção longa para baixo das duas.

### Título mais perto da seção anterior *(Qualidade)*
O título fica mais perto do bloco anterior que do próprio conteúdo. Dê mais espaço acima que abaixo.

### Layout de métrica no hero *(AI slop)*
Número gigante + rótulo pequeno + estatísticas é template de landing. Lidere com métrica quando ela explica o produto.

### Grids de cards idênticos *(AI slop)*
Ícone + título + texto repetidos dão o mesmo peso a tudo. Agrupe ideias e varie o layout quando o conteúdo pede tratamento diferente.

### Espaçamento monótono *(AI slop)*
Espaços iguais em tudo dificultam ver o que pertence a quê. Mantenha o que é relacionado junto e mais espaço entre grupos.

### Cards aninhados *(AI slop)*
Card dentro de card cria ruído e profundidade. Achate: use espaçamento, tipografia e divisórias em vez de contêineres.

### Linha de texto longa demais *(Qualidade)*
Linhas longas dificultam achar o começo da próxima. Mire 65–75 caracteres e ajuste para fonte e tela.

### Conteúdo vazando do contêiner *(Qualidade)*
Conteúdo transborda ou gera scroll lateral. Deixe o texto quebrar e os elementos encolherem; use região rolável quando precisar.

### Menus/popovers cortados *(Qualidade)*
Um contêiner corta menu, tooltip ou popover. Permita o overflow, ou renderize a camada fora do contêiner que corta.

---

## 6. Movimento

### Ponto de status pulsando *(AI slop)*
Ponto pulsando chama atenção mesmo quando nada muda. Status parado fica parado; movimento sinaliza atividade que importa.

### Cursor piscando decorativo *(AI slop)*
Cursor piscando faz texto estático parecer editável ou terminal. Remova de copy estático; mantenha onde dá para digitar.

### Marquee com rolagem automática *(AI slop)*
Texto/logos rolando sozinhos fazem a pessoa ler no ritmo da página. Deixe parado, ou dê controle para pausar.

### Easing de bounce/elástico *(AI slop)*
Diálogo que quica ou ultrapassa deixa uma ação banal afetada. Deixe assentar rápido; movimento lúdico só em momento que cabe.

---

## 7. Texto (copy)

### Mesmo texto repetido num contêiner *(Qualidade)*
O mesmo rótulo aparece em vários lugares de um card. Mantenha uma vez, onde importa.

### Abuso de travessão *(AI slop)*
Travessão em toda frase é hábito de IA. Use ponto final entre ideias separadas e outra pontuação quando facilitar.

### Alegações de marketing genéricas *(AI slop)*
"Supercharge" e "world-class" prometem sem explicar. Diga o que a pessoa consegue fazer e o que melhora para ela.

### Contraste forçado ("Não é X. É Y.") *(AI slop)*
Repetir "não é feature, é plataforma" faz tudo soar slogan. Explique a distinção quando importa, e diga o útil direto.

### Chamar algo de "teatro" *(AI slop)*
Chamar de "theater" substitui explicação por desdém. Nomeie o que é ineficaz e explique por quê.

---

## 8. Imagens

### Ilustrações estilo placeholder *(AI slop)*
Cena feita de círculos e blocos genéricos parece arte provisória. Use imagem que diga algo específico do produto.

### Máscaras de imagem serrilhadas *(Qualidade)*
Máscara serrilhada imita borda rasgada sem capricho. Use recorte pronto para o efeito, ou um crop limpo.

### Imagens escondidas sob overlays *(Qualidade)*
Overlay quase opaco esconde a imagem. Reduza até a imagem contribuir, ou remova uma imagem sem propósito.

### Imagem quebrada/placeholder *(Qualidade)*
Imagem vazia ou placeholder deixa a página inacabada. Adicione o asset e confira que carrega, ou remova.

---

## 9. Qualidade geral

### Erros de JavaScript ao carregar *(Qualidade)*
Erro não tratado quebra controle ou esconde conteúdo. Corrija antes de polir a aparência.

### Conteúdo preso esperando aparecer *(Qualidade)*
Conteúdo fica escondido quando a animação de entrada falha. Deixe visível por padrão para a página funcionar mesmo assim.

### Padding apertado *(Qualidade)*
Texto colado em botão ou borda parece espremido. Use a escala de espaçamento para separar conteúdo do contêiner.

### Texto do corpo encostando na borda *(Qualidade)*
Parágrafos precisam de respiro nas laterais. Adicione padding horizontal e confira em larguras estreitas.

### Texto justificado *(Qualidade)*
Justificado cria vãos entre palavras. Alinhe à esquerda, ou use hifenização e confira o espaçamento em cada tela.

### Texto de baixo contraste *(Qualidade)*
Texto que se mistura ao fundo é difícil de ler. Suba para WCAG AA: 4,5:1 no normal e 3:1 no grande.

### Nível de heading pulado *(Qualidade)*
Hierarquia de headings guia leitores de tela. Siga a estrutura: h2 sob h1, h3 sob h2.

### Line-height apertado *(Qualidade)*
Linhas coladas dificultam seguir o parágrafo. Comece em ~1,5× o tamanho da fonte e ajuste.

### Texto do corpo minúsculo *(Qualidade)*
Corpo pequeno torna a leitura um fardo. Comece em ~16px e confira na fonte real em celular e desktop.

### Espaçamento de letras largo no corpo *(Qualidade)*
Letras afastadas demais dificultam ler parágrafos. Mantenha o corpo perto do padrão da fonte; espaçamento largo só em rótulos curtos.

---

## 10. Tells da comunidade

> Fontes: [godobject.dev — 10 tells of a slop UI](https://godobject.dev/blog/10-tells-of-slop/), a discussão no [Hacker News](https://news.ycombinator.com/item?id=49867038) e threads no Reddit ([r/UXDesign](https://www.reddit.com/r/UXDesign/comments/1s1guo5/), [r/vibecoding](https://www.reddit.com/r/vibecoding/comments/1s37qlp/)). Complementos aos padrões acima; onde sobrepõe, anoto.

### Arco-íris de cores (rainbow vomit) *(AI slop)*
Cores diferentes que não significam nada, só para distinguir campos. Não segue a regra 70-30-10. Feche a paleta: cor só quando o dado pede, com papel consistente. *(relaciona com "Paleta de cor de IA" e "Paleta fechada" em Ofício.)*

### Card "unha" (fingernail card) *(AI slop)*
Um card arredondado com uma aba/faixa colorida no topo que não marca nada — a "unha". Remova a aba quando não há status; deixe o conteúdo definir o card. *(relaciona com "Borda lateral de destaque".)*

### Emoji em tudo *(AI slop)*
Emojis espalhados — ✨ no título, 🚀 no botão, 😊 no vazio. Decoram sem dizer nada. Remova, ou use com moderação extrema; o visual e o texto já comunicam.

### Elemento desalinhado *(AI slop)*
SVG, ASCII art ou elemento fora de caixa quase sempre sai do alinhamento. Confira o alinhamento óptico (ícones e círculos centralizados pelo olho), não só pela caixa. *(relaciona com "Alinhamento óptico" em Ofício.)*

### Badge de status redundante *(AI slop)*
Badge "ativo"/"verificado"/"online" que nunca muda — se não estivesse ativo, a pessoa nem estaria vendo. Só mostre status quando há um estado que de fato varia. *(relaciona com "Ponto de status pulsando" e "Pílula sem função".)*

### `//` prefixado em termos de tech *(AI slop)*
Adicionar `//` antes de qualquer palavra que lembre tecnologia ("// interoperável") é enfeite de "cara de código". Remova; escreva o termo normal.

### Texto que vaza o prompt *(AI slop)*
Texto que denuncia o comando que o gerou: "Built with Hugo. Written from Neovim", "one campus. one app.", "3 apps em 1". Ninguém liga para a ferramenta ou para o briefing. Escreva o que a pessoa ganha, não o processo. *(relaciona com "Mesmo texto repetido" e "Explicação óbvia da origem".)*

### Saudação com ✨ / tela tratada como landing *(AI slop)*
"Welcome to your Dashboard, [Nome] ✨" e subtítulo cinza prometendo "experimente o poder de...". Tratar ferramenta como landing page. Em ferramenta, vá direto ao que importa; saudação só se agrega. Em tela que recebe a pessoa, ela vale quando traz dado real ("2 plantas para checar hoje").

### Palavras de hype *(AI slop)*
"Elevate", "Seamless", "Next-Generation", "Supercharge", "Unleash", "Empower" e equivalentes. Prometem sem explicar. Diga o que a pessoa consegue fazer e o que melhora. *(estende "Alegações de marketing genéricas".)*

### Negação suspeitamente específica *(AI slop)*
Quando você pede para não fazer algo, o modelo faz questão de dizer que não fez ("sem mocks", "não usei X"). É o over-indexing do prompt. Remova a autodefesa; ela só confirma o comando.

### Verde-esmeralda é o novo roxo *(AI slop)*
A cor de destaque padrão da IA mudou do roxo para o verde-esmeralda — mas é o mesmo "default de IA", só trocou de cor. Use a cor da identidade do produto, não a da moda do modelo. *(relaciona com "Paleta de cor de IA".)*

### O look "shadcn / default SaaS" *(AI slop)*
Os mesmos cantos arredondados, fundo cinza-neutro, sombras sutis, fonte Inter e a estética "SaaS moderno" — o default de shadcn/ui, Bootstrap e Tailwind. Tudo que usa a biblioteca sem customizar vira igual. Escolha uma estética com intenção, não a média estatística. *(relaciona com "Fonte saturada" e "Sombra/raio iguais".)*

### Esqueleto padrão de landing *(AI slop)*
Hero → grade de features → prova social → preços → FAQ → footer, sempre na mesma ordem. É a estrutura de todo exemplo de shadcn/Tailwind/Vercel, e o modelo a reproduz por padrão. Deixe o conteúdo ditar a estrutura, não o template. *(relaciona com "Grids de cards idênticos" e "Layout de métrica no hero".)*

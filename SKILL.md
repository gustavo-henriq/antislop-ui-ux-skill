---
name: deslop
description: Tira o "AI slop" de uma interface que já existe, ou cria uma interface nova sem ele. Use quando o pedido for redesenhar, refinar, "des-ai-slopar", animar, criar variações ou desenhar uma tela nova. Lê o gosto do usuário (gosto.md), entende o papel da tela, identifica os sinais, pergunta, propõe um wireframe cinza, implementa, faz o acabamento e roda uma segunda checagem. Quando o usuário pedir inspiração, busca exemplos nas fontes curadas (fontes-de-referencia.md) e filtra tudo pelo acervo anti-slop (anti-slop/ + estetica-ia.md).
---

# Des-ai-slopar uma interface

Uma tela "slop" parece montada por alguém que não usa o produto: todos os blocos com o mesmo peso, texto explicando o que um desenho mostraria, ações repetidas e enfeites que não dizem nada. O objetivo é que cada elemento exista por um motivo que o usuário perceba.

> Esta skill é a **versão canônica e genérica**. Cada projeto que a adota mantém, dentro da própria pasta do projeto, os arquivos **`gosto.md`** (escolhas e recusas) e **`receitas.md`** (paleta e componentes). O resto mora aqui.

## Quando NÃO usar

Esta skill não é para:

- **Bug ou comportamento de código.** Se algo quebra, não responde ou dá erro, é tarefa de código, não de desalopar.
- **Conteúdo ou texto puro.** Revisar copy/texto sem uma tela não é desalopar.
- **Decisão de produto sem tela.** "O que lançar", "qual preço", "qual recurso" sem desenhar uma tela.
- **Só opinião ou resumo.** Se o usuário quer apenas avaliar o que já existe sem redesenhar, responda direto — só acione o ciclo se ele pedir mudança.

Na dúvida, pergunte o que o usuário quer: uma tela nova, redesenhar uma que existe, ou só avaliar.

## Duas direções, o mesmo ciclo

A skill serve para duas coisas, e o pedido diz qual:

- **Desalopar uma tela que existe** (no app, no Figma ou um protótipo já feito, inclusive um que a própria skill acabou de implementar). O ponto de partida é a tela atual.
- **Criar uma tela nova** (uma tela que ainda não existe). O ponto de partida é o pedido e a régua (o padrão do produto em `receitas.md`). Se o usuário chegar sem marca, paleta ou componentes, siga *Chegar cru* antes.

As duas seguem o mesmo ciclo. O tamanho do pedido define o modo (ver *Tamanho do pedido*); dentro do modo, nenhuma etapa é pulada:

1. **Entender o papel.** Descubra com o usuário por que a tela existe e onde ela fica no fluxo, antes de qualquer desenho (ver *Papel da tela*).
2. **Identificar.** Na tela que existe: a *Auditoria* apontando cada sinal no lugar. Na tela nova: o que a tela precisa resolver, o que já existe no produto sobre isso e o que está faltando.
3. **Perguntar.** Pare e pergunte ao usuário (ver *Perguntar é o principal*). Nunca troque uma pergunta por uma suposição.
4. **Propor um wireframe.** Esqueletos cinza em HTML, sem cor e sem fonte da marca, com duas organizações quando a direção não estiver clara. Mostre o print e pergunte qual segue. É barato mudar aqui; depois de implementado, não.
5. **Implementar.** O protótipo na paleta e nas receitas do projeto, seguindo o wireframe escolhido, com os ajustes que o usuário pedir.
6. **Acabamento.** Com a tela aprovada, dê luz, forma e volume na dose que o usuário escolher (ver *Acabamento*).
7. **Segunda checagem: desalopar a versão final.** Rode a skill de novo sobre o protótipo pronto, na direção "desalopar", como se a tela fosse de outra pessoa: *Auditoria*, checklist de `estetica-ia.md`, *Teste de redundância*, *Ofício*, comparação com a régua e com a frase do *Papel da tela*. Depois vem o *Olhar de fora*. Deixe de fora as exceções registradas em `gosto.md`. Mostre a lista do que achou e pergunte o que corrigir antes de mexer: o próprio desenho também entra slop sem perceber.

## Tamanho do pedido

Antes de começar, diga qual modo o pedido parece ser e confirme com o usuário. As perguntas valem nos três modos.

| Modo | Quando usar | O que roda |
|---|---|---|
| **Ajuste** | Muda um elemento ou detalhe, e a organização da tela continua igual (um botão, um texto, um espaçamento) | Identificar só naquela peça, perguntar, implementar, passar *Teste de redundância* e *Ofício* na peça, registrar o gosto. Sem wireframe, sem variações, sem *Acabamento* e sem *Olhar de fora* |
| **Tela** | Uma tela nova ou redesenhada | O ciclo inteiro, com *Olhar de fora* em print parado |
| **Fluxo** | Várias telas ligadas, com etapas ou ramificações | O ciclo inteiro, com *Olhar de fora* em *Telas com fluxo: todos os caminhos* |

Se um Ajuste começar a mexer na organização da tela ou em outra tela, pare, avise e suba para Tela. Na dúvida entre dois modos, use o maior.

## Papel da tela

Antes de auditar ou desenhar, descubra por que a tela existe e qual é a posição dela no app. Não encaixe a tela numa categoria: investigue com o usuário. Uma tela não é a soma das ações que cabem nela: a Home de um app de rotina pode existir para receber a pessoa, mesmo que também dê para marcar uma tarefa ali.

Pergunte ao usuário, com opções concretas:

- **Por que esta tela existe?** O que o app perderia sem ela?
- **Onde ela fica no fluxo?** De onde a pessoa vem, o que ela faz aqui e para onde vai depois?
- **O que a pessoa precisa sentir ou entender nos primeiros segundos?**
- **O que muda quando ela volta amanhã?**
- **Que tarefa parece pertencer a esta tela, mas mora em outra?**

Feche numa frase e confirme com o usuário:

> Esta tela existe para ___. Ela não é a tela de ___.

Nada de wireframe antes dessa confirmação. Registre a frase em `gosto.md`. Se o motivo da tela mudar depois, volte à estrutura.

**Ter um motivo não é ter uma ação.** Uma tela que recebe a pessoa pode ter um atalho, mas o atalho não define a tela. Uma saudação vale quando traz dado real (ex.: "2 plantas para checar hoje"); saudação sem dado continua sendo enchimento.

## Chegar cru (sem identidade visual)

Quando o usuário chega querendo montar uma interface do zero — sem marca, paleta ou componentes — a skill vira uma **investigação**: ajuda o usuário a direcionar as próprias ideias, sem decidir por ele. Antes de qualquer implementação, pergunte:

- **O que é o projeto?** O produto, serviço ou fluxo do qual a tela faz parte.
- **Já existe identidade visual?** Paleta, tipografia, componentes e tom do texto que o projeto já usa.
- **O que a tela precisa resolver?** A intenção, o objetivo e o que o usuário quer fazer.
- **O que já existe no produto sobre isso?** Telas, fluxos e componentes que podem ser reaproveitados.
- **O que está faltando?** Problemas, lacunas e oportunidades para atender a intenção.

Se **não houver identidade visual**, ajude a criar uma: gere paleta, tipografia, componentes e tom de texto coerentes com o produto. Use `receitas.md` como referência; se estiver vazio, apoie-se nas regras de *Ofício* e nos *Princípios* desta skill. Para fonte, siga `tipografia.md` (indie, sem serifa, com neutras que passam). Se o usuário pedir referências de identidade, use *Identidade e sistemas visuais* em `fontes-de-referencia.md`, sempre como conceito. Mostre um HTML de demonstração das ideias e deixe o usuário decidir — ele guia, você investiga.

Quando o usuário aprovar, grave a identidade em `receitas.md` (paleta, fontes, superfícies, componentes) e as escolhas em `gosto.md`, na pasta do projeto. Sem isso, a próxima tela começa do zero.

## Perguntar é o principal

O usuário considera as perguntas o principal diferencial da skill. Use a ferramenta de perguntas em cada ponto abaixo, com opções concretas e a recomendada primeiro:

- **Modo:** Ajuste, Tela ou Fluxo (ver *Tamanho do pedido*).
- **Direção (se não estiver clara):** tela nova ou refatorar uma que existe? Confirme antes de seguir (ver *Duas direções*).
- **Papel da tela:** a frase "Esta tela existe para ___. Ela não é a tela de ___." (ver *Papel da tela*).
- **Intenção:** o que a tela resolve, em que momento é usada, o que incomoda e o que não pode mudar, além das decisões de produto que só ele toma (quando aparece, o que é pago, o que acontece depois).
- **Problemas da auditoria:** quais sinais ele quer corrigir e quais são gosto dele. O que for gosto dele vira exceção em `gosto.md`.
- **Prioridades:** a job story e a ação, se o papel pedir uma, quando houver dúvida.
- **Wireframe:** qual organização segue.
- **Visual:** cor, fonte, densidade, componentes e tom do texto. Pergunta visual é sempre mostrada, nunca só descrita: cor e fonte aplicadas a um pedaço real da tela.
- **Faltando algo, peça — não invente.** Se para implementar falta uma foto, um vetor/ícone, um dado real, um nome, um texto final, ou uma opinião que só o usuário tem (qual caminho, qual tom, qual prioridade), pergunte antes de prosseguir. Não preencha com placeholder nem chute; se o usuário autorizar um provisório, marque como provisório no HTML e avise o que ficou de fora.
- **O que os avaliadores de fora sugeriram:** função nova sugerida por eles só entra se ele aprovar.
- **Acabamento:** a dose, vendo a tela sem acabamento, com dose leve e com dose média.
- **Antes de corrigir na segunda checagem:** a lista do que foi achado, e ele escolhe.
- **Dúvida nova:** se uma resposta abrir dúvida nova, pergunte de novo antes de seguir.

## Quando o gosto e o checklist discordam

A ordem é: `gosto.md`, depois `receitas.md`, depois esta skill (perfil padrão e checklists incluídos).

- **Exceção registrada vence o checklist.** Se `gosto.md` aprova um sinal, não aponte esse sinal como problema nem pergunte de novo, nem na segunda checagem.
- **Exceção tem alcance.** Registre em *Exceções ao checklist* o sinal, onde vale e o motivo. Fora desse alcance, o sinal volta a contar.
- **Exceção não cobre legibilidade.** Contraste, tamanho de texto e leitura continuam sendo checados, mesmo com o efeito aprovado.
- **Reabra só com motivo.** Só traga a exceção de volta se o usuário pedir ou se o *Olhar de fora* mostrar um problema real de uso. Nesse caso, pergunte; não remova sozinho.
- **Olhar de fora não sabe das exceções.** Ele continua sem contexto. Se apontar algo que é exceção, filtre a resposta depois.

## Processo

Estes passos valem para os modos Tela e Fluxo. No modo Ajuste, prepare o projeto, leia o gosto e a régua e siga o que *Tamanho do pedido* lista.

1. **Preparar o projeto.** Procure `gosto.md` e `receitas.md` na pasta do projeto (em geral `.claude/skills/<nome>/`). Os arquivos com esses nomes nesta skill são só modelos: nunca escreva neles. Se faltar algum, copie o modelo para `<projeto>/.claude/skills/deslop/`, tire da cópia o aviso de modelo no topo e avise o usuário. Se o projeto já tem telas ou uma régua em outro lugar (`DESIGN.md`, tokens no código, uma seção da skill do projeto), preencha `receitas.md` a partir disso e mostre para o usuário confirmar. Se não tem nada, siga *Chegar cru*.
2. **Ler o gosto.** Leia `gosto.md` do projeto (escolhas, recusas e exceções anteriores). Se o projeto tiver referências visuais próprias, leia o README delas.
3. **Abrir a régua.** Antes de desenhar, abra `receitas.md` (paleta, superfícies e componentes do projeto). Derive os componentes da régua; só invente quando ela não tiver nada parecido, e diga ao usuário o que foi inventado. Em tela de app (tabela, métrica, gráfico, chat, formulário, navegação, estados), leia também `componentes.md`. Se a tela usa ou pede vidro ou blur, leia `vidro.md`.
4. **Entender o papel.** Siga a seção *Papel da tela* e confirme a frase com o usuário.
5. **Identificar.** Na tela que existe, liste os sinais das seções *Auditoria* e `estetica-ia.md`, apontando cada um no lugar. Na tela nova, diga o que ela resolve e o que falta hoje. Mostre a lista antes de propor.
6. **Perguntar.** Faça as perguntas de intenção e de problemas.
7. **Responder as perguntas de prioridade.** Escreva as respostas da seção *Perguntas de prioridade* para esta tela.
8. **Wireframe cinza.** Monte os esqueletos, tire um print e pergunte qual organização segue.
9. **HTML antes de implementar ou passar para o Figma.** Protótipo autocontido em HTML (imagens em base64, viewport real, dados de exemplo coerentes com as outras telas). Se a tela tem estados, ela volta ao estado inicial ao entrar de novo.
10. **Variações quando a direção não estiver clara.** Siga a seção *Variações*.
11. **Acabamento.** Com a tela aprovada, siga a seção *Acabamento*.
12. **Segunda checagem.** Rode a skill de novo sobre a versão final, na direção "desalopar": *Auditoria*, checklist de `estetica-ia.md`, *Teste de redundância*, regras de *Ofício*, *Teste dos 2 segundos* e a frase do *Papel da tela*. Compare com a régua e liste cada fuga (cor, fonte, tamanho, card, espaçamento, ilustração).
13. **Olhar de fora.** Na versão final, siga a seção *Olhar de fora*. Junte o resultado à lista da segunda checagem, mostre ao usuário e pergunte o que corrigir.
14. **Corrigir e repetir quando preciso.** Corrija o que o usuário escolher. Se cor, fonte, superfície, estrutura ou animação mudarem depois da última checagem, rode a segunda checagem de novo antes de dar a tela por pronta ou passar para outra. Repita o *Olhar de fora* quando a mudança puder afetar o entendimento.
15. **Contar o que as checagens acharam.** Ao entregar, diga o que a segunda checagem e o olhar de fora encontraram e o que mudou.
16. **Registrar o gosto.** Quando o usuário escolher, recusar ou elogiar, acrescente uma linha em `gosto.md`. Se ele aprovar um sinal do checklist, registre em *Exceções ao checklist*.
17. **Figma é opcional.** Só leve ao Figma quando o usuário pedir, e só depois de aprovar o HTML.

## Buscar inspiração (quando o usuário pedir)

Dispara quando o usuário pedir algo como "me mostra exemplos", "o que você usaria de referência", "me inspira em <tema>", "faz como o <site>". **Não busque por conta própria a cada tela** — só quando pedido.

As fontes de `fontes-de-referencia.md` são, em geral, **bibliotecas de elementos** (UI/UX, landing, fluxos). A busca não é "tirar 3 prints de uma página": é **iterar sobre os elementos** que a fonte oferece — o subagente entra, vê o que existe para buscar (categorias, filtros, busca por palavra-chave) e refina até achar o elemento que responde a pergunta.

### Antes de buscar, peça referências

> **Importante!** Referências ajudam a direcionar a identidade visual da aplicação. Se você já tiver algo em mente, anexar ajuda a chegarmos mais perto do que você espera.

Pergunte ao usuário se ele tem referências (link, print, app de que gosta, "quero a cara do X"). Se tiver, a busca vira **captura** — um print por referência — em vez de descoberta aberta. Se não tiver, siga a descoberta.

### O ciclo

**Investigação → busca → decisão.** A principal define a pergunta com o usuário; o subagente itera nas fontes discutindo com a principal por texto; a principal analisa os prints e decide **wireframe, paleta, hierarquia e componente**.

### Pedido mínimo ao subagente

Antes de chamar o subagente, a principal sempre informa:

- **Produto e público:** o que o app faz e para quem.
- **Plataforma:** celular, tablet, desktop ou web. Ela vem do projeto; se não der para saber, pergunte ao usuário antes de buscar.
- **Tipo de tela:** por exemplo, lista de produtos.
- **Elemento procurado:** o que a referência precisa responder.
- **O que fica de fora:** por exemplo, landing pages.

A escolha das fontes segue a plataforma (ver *Fonte por plataforma* em `fontes-de-referencia.md`).

Separe a busca em dois tipos, nesta ordem:

1. **Função da tela:** telas que fazem o mesmo trabalho (ex.: Home de app de hábito ou autocuidado). Busque pela função, não pela metáfora.
2. **Ideia visual:** a linguagem que se quer explorar (ex.: ilustração de flores). Faça à parte; serve só para a linguagem visual e não conta como referência de estrutura.

### O que conta como referência

O subagente só salva o que passar nos três pontos:

- **É um exemplo aberto,** não uma listagem ou coleção.
- **Tem a mesma função de tela** ou responde à ideia visual pedida.
- **É da plataforma certa.** Na busca de identidade (paleta, tipografia, superfície), a plataforma pode ser outra, porque ali não se aproveita a estrutura.

Ele não julga beleza. O que não passar fica fora dos prints e entra no relatório como "não achei".

### Modo barato × modo guiado (o usuário escolhe)

- **Barato (padrão):** subagente quase autônomo — entra, filtra, tira os prints e devolve. A principal só lê o resultado. Uma rodada de diálogo, poucos tokens. Meta: 5 a 8 prints úteis, de pelo menos 2 fontes.
- **Guiado:** a principal participa do caminho — escolhe filtros e palavras-chave junto com o subagente, passo a passo. Mais tokens e decisões melhores; use quando a peça é crítica ou a direção está em aberto. Meta: 10 a 15 prints úteis, de pelo menos 3 fontes.
- Na dúvida, comece barato e escale só se o resultado não bastar. O usuário decide o modo.

### O diálogo e a descoberta de filtros (só texto)

O subagente e a principal conversam **por texto curto**, nunca colando o conteúdo da página. O sub não inventa o caminho — **lê o que a própria fonte oferece** e propõe a partir disso.

1. **Reconhecimento (1 print).** O sub abre a página de explorar/busca da fonte e tira print. No print ele identifica os controles visíveis — caixa de busca, filtros (chips ou sidebar), categorias, ordenação, abas — e anota os **rótulos exatos** que vê (ex.: "Empty State", "Onboarding", "iOS/Android", "sort by revenue"). Se precisar ler os rótulos, dá um crop na área do filtro.
2. **Mapeamento para a pergunta (texto).** O sub cruza esses rótulos com a pergunta da principal e devolve: (a) o que a fonte permite buscar; (b) **2–3 caminhos concretos** usando os rótulos reais ("filtro padrão → 'empty state'", "busca 'empty'", "categoria 'Productivity'").
3. **Decisão (texto).** A principal escolhe um caminho. No modo **barato**, o sub aplica direto o caminho que ele mesmo classificou como melhor e só reporta; no **guiado**, para e pergunta.
4. **Aplicação (1 print).** Se a fonte tiver filtro de plataforma, o sub aplica esse filtro primeiro. Depois clica/filtra/digita e tira print dos resultados. Se o primeiro print vier da plataforma errada, ele para e avisa a principal, nos dois modos.
5. **Refinamento (máx. 2–3).** Se os resultados não respondem, o sub volta com alternativas — sinônimos, categoria vizinha, termo mais largo ou mais específico — **sempre no vocabulário da própria página** (o índice do site é feito com os rótulos dele, não com sinônimos inventados).
6. **Entrega.** Prints finais + uma linha cada (fonte, o que mostra, animação se houver).

**Regras de palavra-chave:** use o vocabulário da fonte (rótulos/termos da UI), não o seu — se o site é em inglês, busque em inglês mapeando a intenção do PT-BR. Comece pelo mais específico e alargue ("empty state" → "empty" → "states"). Uma lista curta por vez (2–4 termos) para a principal escolher, não 15. Prefira o que a página sugere (autocomplete, exemplos de busca, tags) ao termo chutado. Se a principal conhece o domínio, ela injeta os sinônimos e o sub testa.

### Quem navega, e como

- **IA principal** — define a pergunta, decide o modo, dirige o diálogo e analisa os prints. É a única que julga qualidade e aplica ao projeto. Antes de mostrar ao usuário, descarta o que estiver fora da plataforma.
- **Subagente de referência (mais barato)** — navega, tira prints, salva em `inspiracao/` e devolve uma linha por print. Aplica *O que conta como referência*, não julga beleza e reporta o que não achou.

### Orçamento e regras

1. **Quantidade pelo que é útil.** Siga a meta do modo. A pergunta principal precisa de pelo menos 3 exemplos. Print que não passa em *O que conta como referência* não entra na conta.
2. **Screenshot, não DOM.** O sub captura a imagem da tela — não lê o DOM, a árvore de acessibilidade nem o texto da página (ler a página também torra token, e o print já traz tudo). A exceção é fonte feita para agentes, como os arquivos Markdown do GradientDeck UI: ali, leia o arquivo.
3. **Código só para a técnica.** Se o print não responde *como* fazer um detalhe (o easing, o SVG, o grid), o sub inspeciona **aquele elemento** — nunca a página toda.
4. **Referência vira conceito.** A principal aplica *hierarquia, ritmo, metáfora* ao projeto — nunca cópia de paleta, fonte ou layout literal.
5. **Filtre pelo acervo.** Antes de usar, a principal roda o exemplo por `estetica-ia.md` e `anti-slop/`. Referência boa também vem contaminada.
6. **Sem subagente/browser.** Use `inspiracao/` como fallback e avise o usuário.

### Depois da busca

- **Confira antes de mostrar.** A principal compara o resultado com cada pergunta, nos dois modos. Se a pergunta principal ficou sem resposta, faça outra rodada ou diga claramente o que não achou; nunca complete com algo parecido.
- **Fonte que falhou.** Avise o usuário e sugira outra fonte ou o login. Não siga como se ela tivesse sido consultada.
- **Volte à estrutura.** Se a busca aconteceu depois do wireframe e trouxe referências de função de tela, refaça os esqueletos antes de perguntar qual seguir. Cada esqueleto cita a referência que o inspirou. Mantenha a opção anterior na comparação só se ela ainda fizer sentido.
- A principal analisa os prints e o roteiro. Se o diferencial for uma **animação**, ela é **reproduzida no HTML** — descrever não basta, o usuário precisa sentir para julgar.
- Registre as escolhas em `gosto.md`.

## Auditoria: sinais de slop

- Cards de largura cheia empilhados, todos com o mesmo peso visual.
- A mesma ação repetida em cada linha (um botão por item).
- A mesma ação em dois lugares da tela.
- Ícone genérico de IA (✦, brilhos, varinha) representando uma função.
- Microcopy que explica o óbvio ou repete a mesma frase em cada item.
- Dado estruturado escrito como frase ("Superfície: úmida. Meio: úmida. Fundo: seca.").
- Texto de enchimento: data acima da saudação, títulos que quebram em duas linhas, rótulos truncados.
- Lista genérica com divisor de 1 px como única estrutura.
- Controle que não controla nada: interruptor mostrando estado, pill de "agrupar" sem função.
- Botão de destaque grande demais para uma ação secundária.
- Rótulo que repete o desenho, ou título de card que repete o conteúdo.
- Explicação óbvia da origem do dado ("você contou"); a origem vira ícone ou estilo.
- Duas ações com o mesmo peso quando o estado já decide qual faz sentido.
- **Estética de IA:** além do conteúdo, passe pelo checklist de `estetica-ia.md` (sinal, CSS de assinatura, correção e quando é legítimo). Para os demais padrões, use `anti-slop/catalogo.md`. A galeria `anti-slop/galeria.html` mostra os principais em pares slop → correção, e `anti-slop/referencias/` traz exemplos reais.

## Teste de redundância

Para cada texto da tela, pergunte: um desenho, um ícone, a posição ou outro texto já diz isso? Se sim, o texto sai.

Depois, o contrário: algum texto que sobrou poderia virar elemento visual? Uma data vira um ponto numa linha, uma comparação vira barras, um estado vira cor ou forma, uma lista de partes vira um desenho em camadas. Troque quando o visual disser o mesmo com menos leitura; mantenha o texto só quando ele carrega um dado exato que o visual não mostra (um número, um nome).

## Perguntas de prioridade

Depois do *Papel da tela*, responda por escrito, para a tela em questão, antes de desenhar. Se uma resposta depender de uma decisão de produto, pergunte em vez de supor. Na segunda checagem, confira se o desenho cumpre.

1. **Que tipo de visita é esta?** Transitória (abre, resolve, sai) ou soberana (fica e explora)? Telas transitórias pedem quase nada além da resposta e da ação.
2. **O que a pessoa quer?** "Quando ___, quero ___, para ___". Se o "para" for circular, a frase está errada. Pense no objetivo, não na tarefa.
3. **Como ela entende o estado sem ler?** Qual atributo percebido antes da leitura (cor, forma, posição, movimento) responde a pergunta principal em menos de um segundo?
4. **O motivo da tela pede uma ação? Se pedir, qual é a única que esse estado pede?** Ela fica em destaque, fácil de alcançar (no celular, ao alcance do polegar), e só aparece quando faz sentido. Numa tela que recebe a pessoa, ela pode ser só um atalho, ou nem existir.
5. **Em que ordem vem o resto?** Visão geral, depois o porquê, depois os detalhes sob demanda.
6. **O que pode ficar na periferia?** Quando está tudo bem, a tela fica calma. Quando algo precisa de atenção, sobe ao centro.
7. **Quais ações são etapas da mesma tarefa?** Pense no fluxo, não na tela parada: o que a pessoa faz antes e depois daqui? Ações que sempre acontecem em sequência viram um botão só com passos.

### Estados da tela

Liste os estados que mudam o que a tela mostra e confira a hierarquia de cada um. Desenhe os estados principais e só os outros que mudam a tela de verdade.

### Teste dos 2 segundos

Se a pessoa visse a tela por 2 segundos, ela saberia o estado e o que fazer? É uma regra nossa: em telas transitórias a resposta não pode depender de ler uma frase.

## Olhar de fora

Quem desenhou sabe o que cada elemento significa e nunca acha nada confuso (maldição do conhecimento). Na versão final, depois do *Acabamento* e da segunda checagem, peça a análise de um agente sem contexto:

1. **Tire um print da tela**, sem notas. Chrome headless funciona: `chrome --headless=new --force-device-scale-factor=2 --window-size=470,910 --virtual-time-budget=6000 --screenshot=<arquivo>.png <url>`. Faça também uma versão pequena ou levemente borrada.
2. **Chame um agente novo**, nunca uma cópia desta conversa, com outro modelo. Entregue só os caminhos das imagens e uma linha sobre o produto. Nunca o código, os nomes das classes nem as intenções.
3. **Comece sempre pela mesma pergunta:** "Olhe a versão pequena e diga, em uma frase, sua primeira impressão." Só depois mostre a nítida.
4. **Crie as demais perguntas para esta tela**, a partir das *Perguntas de prioridade*, sem entregar a resposta. Pergunte sempre "para que serve esta tela?". Peça também o que achou confuso e o que viu primeiro.
5. **Compare** as respostas com a frase do *Papel da tela*, com a job story e com as respostas 3 e 4. Onde divergir, o desenho falhou, não o leitor.

### Telas com fluxo: todos os caminhos

Quando a tela é um fluxo com etapas e ramificações, um print parado não basta. Liste todos os caminhos, capture cada um passo a passo (script que toca em ordem e printa após cada passo, com um `index.json`), e rode **um agente novo por caminho** (nunca por passo), pedindo uma tabela por passo (o que comunica, próximo toque esperado, surpresas) e os problemas por gravidade.

### Rodadas

Depois de corrigir, rode de novo com agentes **novos** — um agente que já viu a versão anterior lê a nova com as respostas na cabeça. **Por padrão, uma rodada.** Mais (até três) só quando o usuário pedir ou quando a correção mudar o fluxo ou o entendimento da tela. O agente julga bem a **clareza** e mal a **beleza**; a beleza é decidida pelo usuário, com as *Variações* e o `gosto.md`.

## Ofício: contra o feio

Regras que não garantem o bonito, mas impedem o feio. Confira na segunda checagem. O bonito vem do *Acabamento*.

- **Espaçamento numa escala só** (4, 8, 12, 16, 24, 32…). Nada de valores soltos. Espaço maior entre grupos do que dentro deles.
- **Tipos numa escala com proporção:** poucos tamanhos e no máximo dois pesos por tela. Hierarquia por tamanho e peso, não por cor e caixa-alta juntas. A fonte em si vem de `tipografia.md`.
- **Raios consistentes:** o raio de dentro é o raio de fora menos o espaçamento entre eles.
- **Contraste:** texto principal com contraste AA; texto secundário nunca mais claro que o limite sobre o card.
- **Alinhamento óptico:** ícones e círculos centralizados pelo olho; números em colunas usam algarismos tabulares.
- **Uma superfície só** (receita em `receitas.md`) e no máximo três níveis de profundidade.
- **Paleta fechada:** cores fora da paleta só quando o dado pede, e com o mesmo papel em todas as telas.

## Acabamento

Tirar o slop não deixa a tela pronta: ela pode ficar correta e crua, com cara de SVG e não de app. Esta etapa dá luz, forma e volume, de leve. Só comece com a estrutura e a identidade aprovadas.

- **Uma luz só.** Tudo recebe luz da mesma direção. Sombra suave e tingida pela cor da superfície, nunca preta.
- **Sombra com função.** Só no que flutua ou encosta em algo (painel, botão, um objeto apoiado). No máximo dois níveis.
- **Forma menos geométrica.** Curva na borda de uma cena, sobreposição de elementos e raios com propósito, em vez de retângulos empilhados.
- **Ilustração com volume.** Traço variado ou sem contorno, tons dentro da mesma cor, um pouco de luz e detalhes do objeto real.
- **Degradê só tonal.** Dentro da mesma cor, para dar volume. Nada de arco-íris.
- **Textura leve, quando combinar.** Grão sutil, se o projeto pedir.
- **Continua proibido:** glow externo, blob por blur, sombra igual em tudo e efeito que atrapalhe a leitura.
- **Mostre as doses.** Apresente a tela sem acabamento, com dose leve e com dose média, com os mesmos dados. O usuário escolhe, e a receita aprovada vai para `receitas.md`.
- **Confira a viabilidade.** Antes de perguntar, avise o que a plataforma final consegue reproduzir (o protótipo é HTML; o app pode não ser).

Se o `receitas.md` disser "tudo chapado", pergunte antes de contrariar.

## Consistência entre telas

Antes de inventar um componente, procure se ele já existe em outra tela e reaproveite; se não existir, parta da anatomia em `componentes.md`. O usuário aprende um símbolo numa tela e reconhece nas outras. Um símbolo novo só entra quando nenhum dos existentes diz aquilo, e então passa a valer para todas.

## Voz do texto

- Verbo no começo quando houver uma ação.
- Frases curtas, sem jargão e sem ponto final em rótulos e títulos.
- O dado exato no lugar do adjetivo ("seca 2–4 nov", não "seca em breve").
- No idioma do produto, falando com a pessoa (ver *Perfil padrão*).
- Conselho sem cara de IA: nada de "pede atenção", "vale conferir", "costuma ser". Diga a causa como fato e a ação concreta. E sem caixa colorida em volta do conselho.

## Variações

Use quando a direção não estiver clara ou quando o usuário pedir. Não faça variações em toda tela.

- **Varie um eixo com sentido de cada vez**, nunca só a cor (densidade, hierarquia, metáfora visual).
- **Escolha de pacote não decide tudo.** Se uma opção misturar cor, fonte e superfície, a escolha vale só para o eixo que está sendo perguntado. Pergunte os outros separadamente antes de gravar em `receitas.md`.
- **No máximo três opções, num HTML só**, com uma chave para alternar, mesmos dados e mesmo estado.
- **Cada opção com nome e uma frase de motivo**, citando o fundamento.
- **Comece pelo que o `gosto.md` indica**; referências viram conceito, nunca cópia.
- Quando o usuário escolher, registre em `gosto.md`.

## Fundamentos

Cite o fundamento ao justificar uma decisão. Use os fundamentos ao aplicar as soluções.

- **Reconhecimento em vez de memória (Nielsen #6).**
- **Design estético e minimalista (Nielsen #8).**
- **Visibilidade do status do sistema (Nielsen #1).**
- **Razão dado/tinta (Tufte):** apague a tinta que não é dado e a tinta que repete dado.
- **Significantes (Norman):** um desenho claro dispensa o rótulo.
- **Proximidade e região comum (Gestalt):** o card já agrupa.
- **Lei de Hick e efeito Von Restorff:** uma ação principal por estado.
- **"Don't make me think" (Krug):** corte metade das palavras, depois metade do que sobrou.

## Princípios

- **Mostrar em vez de escrever.** Estado vira cor/forma/posição; não parágrafo.
- **Uma ação, um lugar.** Filtros moram dentro da busca; nada duplicado.
- **O mínimo por item.** Só o que responde a pergunta do item.
- **Hierarquia com pouco elemento.** Número grande só onde ele é a notícia. Saudação numa linha, com um dado real embaixo.
- **Profundidade com uma receita só.** Superfície consistente; sombra só no que flutua.
- **Cor com significado.** Degradê só quando conta algo ou dá volume (ver *Acabamento*).
- **O estado escolhe a ação.** Nunca dois botões equivalentes lado a lado.
- **Status é texto, não controle.** "Ligado" em verde, nunca interruptor decorativo.
- **Ícones e SVGs próprios.** Ícone de UI é sempre SVG próprio, no estilo do produto (`receitas.md`) — nunca genérico de IA (✦, brilhos, varinha) nem de biblioteca pronta. Traço, peso, canto e grade consistentes; o mesmo símbolo vale em todas as telas.
- **Imagem antes de vetor (para arte).** Para ilustração e cena (flor, mascote, textura), gere a **imagem** quando a IA tiver como gerar imagens. Vá de **vetor em SVG** desenhado por você quando ela não tiver essa capacidade ou quando o usuário não gostar da imagem gerada.
- **Telas muito vazias.** Em telas muito vazias, sugira ideias para preencher (animações, cards, etc.). Não implemente sem permissão, mas proponha como forma de prosseguir.

## Movimento

Animação explica uma mudança de estado; ela nunca decora.

- **Causa e efeito.** Algo se move porque algo aconteceu.
- **Continuidade.** O elemento tocado vira a próxima tela.
- **Física de coisa real.** Mola para objetos; ease-out curto (180–400 ms) para interface.
- **Dois fatos, um lugar.** Começo e fim da mesma coisa podem dividir o espaço e trocar.
- **Uma coisa por vez.** Encadeie os passos.
- **Reduzir movimento.** Respeite `prefers-reduced-motion`.
- **Diferencial de referência.** Se a referência tem uma animação que é o diferencial, ela entra no protótipo — descrever não deixa o usuário sentir o diferencial.

Sinais de movimento slop: fade escalonado ao abrir, brilho pulsando em loop, shimmer em degradê, parallax sem função, confete, cards "flutuando" no hover, spinner onde o resultado é instantâneo.

## Universo do produto (efeito temático)

Entenda o **escopo** do produto — o que ele faz, para quem, qual universo (astronomia, música, finanças, saúde…). Todo efeito visual deve **se remeter à ideia** que o produto cumpre, não decorar.

- **A metáfora vem do produto.** App de estrelas → constelações, um degradê que atravessa como cometa, brilho de estrela no foco. App de música → forma de onda, equalizador. App de marés → ondas. App de clima → luz e nuvem. App financeiro → o número como protagonista, sem efeito.
- **Sempre proponha 1–3 efeitos temáticos** ligados ao universo e mostre no HTML de demonstração — não decida sozinho.
- **Sutil e com sentido.** O efeito ambienta ou explica; nunca vira desculpa para glow ou confete sem função. Um efeito de assinatura é um só, não cinco.
- **Não em toda tela.** Focal e com propósito (o mesmo limite do glow).
- **Respeite o movimento reduzido** e a regra do *Movimento*.
- Registre o efeito escolhido em `gosto.md`; se for de marca, em `receitas.md`.

## Receitas

A régua do projeto (paleta, superfícies e componentes) vive em **`receitas.md`**, dentro da pasta do projeto — não aqui. Este arquivo é o template do que preencher lá.

## Perfil padrão

Preferências com que a skill começa. Não são leis: valem até o `gosto.md` ou o `receitas.md` do projeto dizer outra coisa, e podem ser editadas aqui.

- **Idioma do produto:** português do Brasil.
- **Fonte:** sem serifa, indie ou neutra (`tipografia.md`).
- **Vetos de partida:** interruptor decorativo, informação demais num card, rótulo redundante, texto de enchimento, lógica interna à mostra, duas ações equivalentes lado a lado, sombras exageradas, blob de cor por blur, layout de card genérico ("parece template").

Mantenha em `gosto.md` a lista de vetos do projeto.

## Entregáveis

Ao fechar um ciclo, entregue (e confira se nada ficou de fora). No modo Ajuste, bastam a lista de correções e o `gosto.md` atualizado:

- **Papel da tela** — a frase confirmada com o usuário.
- **Auditoria** — a lista de sinais encontrados, apontados no lugar.
- **Wireframe cinza** — o(s) esqueleto(s) aprovado(s).
- **Protótipo HTML** — a tela implementada, autocontida, com os estados.
- **Lista de correções** — o que a segunda checagem e o olhar de fora encontraram e mudaram.
- **`gosto.md` atualizado** — escolhas, recusas e referências novas registradas.
- **(opcional) Figma** — só quando o usuário pedir, depois de aprovar o HTML.

---

Feito por [Guto](https://byguto.com) · [@henrik404](https://x.com/henrik404)
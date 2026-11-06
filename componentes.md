# Componentes de produto sem cara de IA

Anatomia de componente para telas de app (dashboard, painel, chat, tabela) — não para landing. É o complemento de `fontes-de-referencia.md`: lá ficam os sites; aqui fica **como o componente se organiza** para não parecer template.

> Referência principal: [BoardUI](https://www.boardui.com/pt-br) — sistema de design React com 103 componentes, 19 gráficos e tokens para dashboards e interfaces de agentes. O que se aproveita é a **estrutura, o comportamento e os estados**. A estética default (cinza-neutro + Inter + cantos iguais) é o "look shadcn" do `anti-slop/catalogo.md`: se a identidade do projeto for outra, troque a pele e mantenha o esqueleto.

## Regra de uso

- Copie **anatomia** (o que existe, em que ordem, com que peso), não pixels.
- Todo componente sai de `receitas.md`: cor, tipo, raio, sombra e espaço da identidade.
- Antes de criar um componente, procure se ele já existe em outra tela (ver *Consistência entre telas*).
- Estado é parte do componente: vazio, carregando, erro, sucesso. Componente sem estado é maquete.

---

## Tabela de dados

A peça em que mais se vê slop: tudo com o mesmo peso, status decorativo e ação repetida.

**Anatomia que funciona**
1. **Cabeçalho com o total** — "48 clientes" e não "Resultados totais" sozinho.
2. **Filtros antes da tabela**, na ordem em que a pessoa decide: busca → filtro de status → período. Um "limpar" discreto quando há filtro ativo.
3. **Coluna de identidade** (nome + avatar/inicial) primeiro; números alinhados à direita e com algarismos tabulares.
4. **Status como texto curto**, com cor só quando o estado muda de verdade. Nunca pílula colorida em toda linha.
5. **Ações da linha** discretas e no fim; a ação principal fica na barra, não repetida em cada linha.
6. **Paginação explícita** com o intervalo atual ("1–20 de 48").

**Descarte:** zebra + borda + sombra juntas, ícone em cada coluna, badge "ativo" em tudo, botão cheio por linha, linha clicável que não parece clicável.

## Tile de métrica

**Anatomia que funciona:** número grande (o dado manda) → rótulo curto embaixo → comparação com período e direção (↑ 14,8% vs. mês anterior) → uma frase de contexto quando ajuda a agir. Um tile = uma pergunta.

**Descarte:** número gigante com rótulo minúsculo e nenhum contexto; gradiente no número; três tiles idênticos só para preencher a primeira dobra.

## Card de gráfico

**Anatomia que funciona:** título que diz o que o gráfico responde → seletor de período (dia/semana/mês/ano) → gráfico → legenda curta → leitura do dado ("pico em março"). Um card, uma pergunta.

**Descarte:** donut/anel decorativo, gradiente de preenchimento sem significado, eixos sem unidade, tooltip que repete o rótulo, "widget brincalhão" (streak, anel de atividade) quando não é o produto.

## Interface de agente (chat/painel de IA)

**Anatomia que funciona**
- **Composer** com anexo, modelo e envio no mesmo lugar; estado de envio explícito.
- **Progresso por etapa** com nome e estado (feito / em andamento / falhou) — não um spinner genérico.
- **Fonte consultada** aparece junto da resposta, não escondida atrás de um ícone.
- **Custo/limite** (tokens, contexto, plano) em linguagem de uso, não de infraestrutura.
- **Interromper** sempre disponível enquanto o agente trabalha.

**Descarte:** "Agente pensando…" com três pontinhos eternos, brilho iridescente em volta do composer, badges "online" que nunca mudam, emoji no lugar de estado.

## Formulário e upload

**Anatomia que funciona:** rótulo sempre visível (não só placeholder) → campo → ajuda curta → erro no campo, com a causa e o que fazer. Upload aceita arrastar, mostra o tipo/tamanho aceito antes e o progresso por arquivo depois.

**Descarte:** validação só no envio, erro em banner no topo sem apontar o campo, ícone de nuvem genérico, "Enviando…" sem progresso.

## Navegação / sidebar

**Anatomia que funciona:** grupos com título curto, item ativo com contraste (não só cor), busca quando há muitos itens, conta/configuração no rodapé. Badge só quando há contagem que muda.

**Descarte:** ícone em quadrado para cada item, item ativo com glow, sidebar com card dentro, "Novo" piscando.

## Estados vazios, carregando e erro

- **Vazio:** diga o que aparece ali e a ação para criar o primeiro item. Sem ilustração de mascote, sem "Ops!".
- **Carregando:** esqueleto com a forma do conteúdo real (não barra genérica) e nada de shimmer colorido.
- **Erro:** o que falhou, por quê e o que fazer; preservar o que a pessoa digitou.
- **Conteúdo dependente de animação:** visível por padrão; a animação só melhora, nunca revela.

## Checks rápidos por componente

- O componente responde a **uma** pergunta?
- O dado principal tem mais peso que o rótulo?
- Existe estado vazio/carregando/erro?
- A cor só aparece quando o dado pede?
- A ação principal aparece uma vez, no lugar certo?
- O componente usa os tokens de `receitas.md` (cor, tipo, espaço, raio)?

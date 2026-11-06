# Tipografia sem cara de IA

A fonte é o sinal de slop que mais entrega o produto: é a primeira coisa que a pessoa vê e a mais fácil de reconhecer como "gerado". A regra é **preferir fontes independentes e menos conhecidas**, evitar as serifadas e reservar uma lista curta de neutras bem trabalhadas que passam despercebidas (Inter, por exemplo — tem cara de IA, mas por lembrar a SF, a fonte de sistema da Apple, passa levemente batido).

## Regras

1. **Prefira indie/less-known.** Uma fonte que todo template usa denuncia o produto na hora. Fontes de estúdios independentes dão personalidade sem esforço.
2. **Evite serifa no padrão.** Sem serifa para corpo e UI. Serifa só quando o produto é editorial de verdade (jornal, revista, portfólio de texto longo) — e aí como acento, não como default. É preferência do *Perfil padrão*: se o `gosto.md` do projeto escolher serifa, vale a escolha dele.
3. **Neutra pode ser a âncora.** Inter e a pilha do sistema (SF Pro / Segoe / Roboto) passam despercebidas e são a escolha segura quando o projeto quer cara de "app oficial".
4. **No máximo duas famílias.** Uma display (títulos) + uma de texto. Se usar display indie, pareie com neutra de texto.
5. **Vem do `receitas.md`.** A fonte escolhida entra na régua do projeto, com pesos e tamanhos. Não troque por tela.
6. **Confira a licença.** Google Fonts e Fontshare são livres; algumas indie (Söhne, Untitled Sans) são pagas — só use se o projeto tiver licença.

## O que usar

### Indie / menos conhecidas (personalidade)

- **Satoshi** — grotesca neutra, muito versátil (Fontshare).
- **General Sans** — geométrica limpa (Fontshare).
- **Switzer** — grotesca suíça, excelente para corpo (Fontshare).
- **Cabinet Grotesk** — forte para títulos (Fontshare).
- **Clash Display** — display só (títulos), não para texto (Fontshare).
- **HK Grotesk** — sólida e pouco usada (Google).
- **Archivo** — família ampla, com variáveis (Google).
- **Instrument Sans** — neutra contemporânea (Google).
- **Aspekta** — grotesca moderna e discreta (gratuita, site próprio).
- **Onest** — geométrica humanista (Google).
- **Cal Sans** — display com caráter, bom acento (gratuita).

### Neutras que passam despercebidas (cara de fonte de sistema)

- **Inter** — lembra a SF da Apple; neutra e segura (Google).
- **Pilha do sistema** — `-apple-system`, `SF Pro`, `Segoe UI`, `Roboto` — sem cara de fonte nenhuma, porque é a do dispositivo.
- **Manrope** — geométrica que vira neutra (Google).
- **Figtree** — limpa e discreta (Google).
- **Poppins** — geométrica redonda que virou padrão; passa sem cara de IA (Google).

### Premium (só com licença)

- **Söhne**, **Untitled Sans** — as neutras "de estúdio" por trás de muita marca grande. Custo alto; valem quando o projeto pede identidade forte.

## O que evitar (cara de IA imediata)

- **Montserrat, Raleway, Lato, Open Sans** — o slop clássico de template.
- **Plus Jakarta Sans, Outfit, Sora, Space Grotesk, Bricolage Grotesque** — a cara do "SaaS moderno gerado".
- **Geist** — a fonte da Vercel; entrega IA na hora, salvo se o produto for ferramenta de dev e você a assumir de propósito.
- **DM Sans, Urbanist** — já caminham para o saturado; use com cautela.

## Emparelhamento rápido

| Personalidade | Display | Texto |
|---|---|---|
| Neutra / app oficial | Inter (semibold) | Inter (regular) |
| Moderna indie | Clash Display / Cabinet Grotesk | Satoshi / Switzer |
| Editorial (exceção) | serifa do projeto | neutra sem serifa |
| Dev tool | Geist (assumido) | Geist |

## Checks

- A fonte tem personalidade ou é a primeira que o modelo sugere?
- Duas famílias no máximo?
- Serifa apareceu fora de um produto editorial?
- A fonte está no `receitas.md` (pesos e tamanhos fixos)?
- Licença liberada para o projeto?

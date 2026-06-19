---
name: Hanna
description: Painel pessoal de nutrição e treino — números grandes, energia esportiva, zero punição.
colors:
  olive: "#CBD77E"
  olive-deep: "#a8b85e"
  olive-light: "#edf5d0"
  hazel: "#E6CA9A"
  hazel-deep: "#c4995a"
  hazel-light: "#faf3e8"
  ink: "#282828"
  muted: "#888888"
  muted2: "#BBBBBB"
  bg: "#F7F7F7"
  card: "#FFFFFF"
  card-edge: "#EBEBEB"
typography:
  display:
    fontFamily: "Anton, sans-serif"
    fontSize: "58px"
    fontWeight: 400
    lineHeight: 0.95
    letterSpacing: "0.01em"
  headline:
    fontFamily: "Anton, sans-serif"
    fontSize: "24px"
    fontWeight: 400
    lineHeight: 1.02
    letterSpacing: "0.01em"
  title:
    fontFamily: "Manrope, system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 800
    lineHeight: 1.2
  body:
    fontFamily: "Manrope, system-ui, sans-serif"
    fontSize: "14px"
    fontWeight: 600
    lineHeight: 1.5
  label:
    fontFamily: "Manrope, system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 800
    letterSpacing: "0.14em"
    lineHeight: 1.2
rounded:
  sm: "10px"
  md: "14px"
  lg: "20px"
  xl: "24px"
  sheet: "28px"
  pill: "100px"
spacing:
  xs: "8px"
  sm: "12px"
  md: "18px"
  lg: "34px"
components:
  button-primary:
    backgroundColor: "{colors.olive-deep}"
    textColor: "#ffffff"
    rounded: "{rounded.md}"
    padding: "14px"
  button-secondary:
    backgroundColor: "{colors.bg}"
    textColor: "{colors.muted}"
    rounded: "{rounded.md}"
    padding: "14px"
  button-outline:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.sm}"
    padding: "12px 10px"
  chip:
    backgroundColor: "{colors.card}"
    textColor: "{colors.ink}"
    rounded: "{rounded.sm}"
    padding: "8px 12px"
  card:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.xl}"
    padding: "18px"
  input:
    backgroundColor: "{colors.bg}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "12px 14px"
---

# Design System: Hanna

## 1. Overview

**Creative North Star: "O Placar Pessoal"**

O app é o placar do jogo da Hanna. Cada tela responde "como estou hoje?" com a clareza de um marcador esportivo: números gigantes em Anton condensada são os protagonistas, e todo o resto — labels, chips, listas — existe para dar contexto a eles. A energia é esportiva e direta, mas nunca agressiva: o placar celebra pontos marcados, não pune erros. Déficit calórico, peso e treinos concluídos aparecem como conquista em oliva, jamais como alerta vermelho.

A densidade é de app mobile de uso diário: coluna única de no máximo 460px, cards generosos de canto bem arredondado (24px), uma mão no polegar. O sistema rejeita explicitamente o que PRODUCT.md proíbe: nada de "app de dieta punitivo" (sem vermelho de meta estourada, sem culpa) e nada de "infantilizado/gamificado demais" (sem mascotes, confete ou badges decorativos — o progresso real é a recompensa).

**Key Characteristics:**
- Números como protagonistas: Anton uppercase em 36-58px para todo valor que importa
- Fundo claro neutro (#F7F7F7) com brilhos radiais sutis de oliva e mel
- Tátil e responsível: todo elemento interativo reage ao toque com scale e easing custom
- Conquista em oliva, atenção em mel — nunca alarme
- Mobile-first absoluto: safe-areas, bottom nav fixo, sheets que sobem de baixo

## 2. Colors

Paleta de duas vozes sobre neutros limpos: oliva carrega energia e progresso, mel carrega atenção calorosa.

### Primary
- **Oliva Elétrico** (#CBD77E, deep #a8b85e, light #edf5d0): a cor do progresso e da conquista. Preenche barras de kcal, marca treinos concluídos (toggle e calendário), colore os números de gasto energético e o estado ativo do bottom nav. O degradê `linear-gradient(90deg, #a8b85e, #CBD77E)` é a assinatura das barras de progresso.

### Secondary
- **Mel Torrado** (#E6CA9A, deep #c4995a, light #faf3e8): atenção sem alarme. Veste o card de déficit calórico, observações de exercício e o número de ganho de peso. É a única voz para "preste atenção aqui" — vermelho não existe neste sistema.

### Neutral
- **Tinta** (#282828): texto principal e títulos; também o fundo do botão "treino finalizado".
- **Névoa** (#888888) e **Névoa Clara** (#BBBBBB): labels, metadados e hints. Névoa Clara nunca em texto essencial — só em informação descartável.
- **Palco** (#F7F7F7): fundo do body, com dois brilhos radiais fixos (oliva 18%, mel 12%) que aquecem sem tingir.
- **Cartão** (#FFFFFF) sobre **Fio** (#EBEBEB): toda superfície elevada é branco puro com borda de 1px em Fio.

### Named Rules
**The Conquista-Não-Culpa Rule.** Oliva = progresso, Mel = atenção. Vermelho é proibido para dados nutricionais. Estourar a meta é informação em Mel, nunca alarme.

**The Uma-Voz-Por-Card Rule.** Cada card fala uma cor de destaque só. Card de déficit é Mel; card de gasto é Oliva. Nunca os dois competindo na mesma superfície.

## 3. Typography

**Display Font:** Anton (com sans-serif fallback)
**Body Font:** Manrope (com system-ui fallback), pesos 400-800

**Character:** Par de contraste máximo — Anton condensada, uppercase e monolítica para números e títulos de impacto; Manrope arredondada e amigável para todo o resto. O contraste é o sistema: se é Anton, importa; se é Manrope, explica.

### Hierarchy
- **Display** (Anton 400, 54-58px, line-height 0.9-0.95, uppercase): o nome no hero e os números-placar (gasto de hoje, déficit). Encolhe no header sticky ao rolar.
- **Headline** (Anton 400, 22-28px, line-height 1.02, uppercase): títulos de treino e estados vazios.
- **Number** (Anton 400, 16-46px): toda métrica — kcal de refeição, stats, peso. Tamanho proporcional à importância.
- **Title** (Manrope 700-800, 14.5-17px): nomes de refeição/exercício, títulos de modal.
- **Body** (Manrope 600, 12.5-14px, line-height 1.4-1.5): texto corrido, insights, descrições.
- **Label** (Manrope 800, 11-13px, letter-spacing 0.12-0.14em, uppercase): cabeçalhos de seção com dot oliva, labels de modal.

### Named Rules
**The Anton-É-Dado Rule.** Anton aparece exclusivamente em números e títulos de impacto. Texto corrido, botões e labels são sempre Manrope. Um parágrafo em Anton é um bug.

## 4. Elevation

Sistema de camadas suaves: superfícies brancas flutuam sobre o palco cinza com sombras ambientais difusas — nunca dramáticas. A elevação real acontece nas camadas fixas (header sticky, bottom nav, sheets), que usam blur de backdrop (12-16px) sobre branco translúcido para se separar do conteúdo que rola por baixo.

### Shadow Vocabulary
- **Repouso** (`box-shadow: 0 2px 16px rgba(0,0,0,.06)`): cards e stats em estado normal.
- **Repouso leve** (`0 2px 12px rgba(0,0,0,.05)`): cards menores (exercício, lista de concluídos).
- **Hover** (`0 6px 28px rgba(0,0,0,.10)`): só em dispositivos com ponteiro fino, gated por `@media(hover:hover)`.
- **Brilho de conquista** (`0 2px 8-12px rgba(168,184,94,.4)`): toggles e dias marcados — a sombra é oliva, não preta.
- **Nav flutuante** (`0 -2px 20px rgba(0,0,0,.05)` + `backdrop-filter: blur(16px)`): bottom nav.

### Named Rules
**The Sombra-Sussurra Rule.** Sombra preta nunca passa de 10% de opacidade. Se a sombra chama atenção, está errada — destaque é trabalho da cor e do tamanho do número.

## 5. Components

Filosofia: **tátil e responsível** — todo elemento interativo confirma o toque no mesmo instante, com `scale(.88-.985)` no `:active` e easing custom (`cubic-bezier(0.23,1,0.32,1)`). Hover existe só atrás de `@media(hover:hover) and (pointer:fine)`.

### Buttons
- **Shape:** cantos bem arredondados (14-16px)
- **Primary:** fundo Oliva Deep (#a8b85e), texto branco, Manrope 800 14-15px, padding 14-16px, full-width em modais
- **Active:** `scale(.97)` + opacity .9; botão "finalizar treino" vira Tinta (#282828) quando concluído
- **Secondary:** fundo Palco (#F7F7F7), texto Névoa, borda 1.5px Fio
- **Outline (peso):** transparente com borda 1.5px Tinta, uppercase tracked; inverte para fundo Tinta no toque

### Chips
- **Style:** fundo branco, borda 1px Fio, raio 12px, Manrope 700 13px, valor em Oliva Deep 800
- **State:** chip de peso destacado com fundo Oliva Light e borda Oliva; hover eleva a borda para Oliva

### Cards / Containers
- **Corner Style:** 24px (cards principais), 22px (treino), 18px (exercício/listas)
- **Background:** branco; o card de déficit usa degradê Mel Light (155deg, #faf3e8 → #fdf6ec) com borda #f0dfc0
- **Shadow Strategy:** Repouso (ver Elevation); glow decorativo blurrado (140px, blur 50px) no canto dos stats
- **Border:** sempre 1px Fio — a borda define, a sombra flutua
- **Internal Padding:** 18px

### Inputs / Fields
- **Style:** fundo Palco, borda 1.5px Fio, raio 10-14px, Manrope 700-800 16px (evita zoom no iOS)
- **Focus:** borda vira Oliva Deep; inputs de série ganham fundo branco
- **Done:** série concluída pinta borda Oliva e fundo Oliva Light

### Navigation
- **Bottom nav fixo:** branco translúcido (.94) com blur 16px, borda superior Fio, safe-area respeitada; 4 abas (Início/Treino/Chat/Progresso) com ícone 26px + label 11.5px; ativo em Oliva Deep, inativo em Névoa Clara; ícone faz `scale(.88)` no toque
- **Header sticky:** encolhe ao rolar (58px → menor), fundo translúcido com blur 14px

### Sheets & Modals (signature)
Toda edição acontece em bottom sheets: sobem de baixo com `cubic-bezier(0.32,0.72,0,1)` (ease-drawer), raio 28px só no topo, handle de 40x4px, overlay escuro 35% com blur 4px. O detalhe de treino é um sheet full-screen com header e footer próprios em blur.

### Accordion (signature)
Seções colapsáveis com `grid-template-rows: 0fr → 1fr` (380ms), header que funde com o corpo aberto (raio 20px → 20px 20px 0 0), seta que rotaciona 180° e pinta de Oliva Deep.

## 6. Do's and Don'ts

### Do:
- **Do** usar Anton uppercase para todo número que importa — o placar é o produto.
- **Do** confirmar todo toque com `scale` no `:active` e a curva `--ease-out` (cubic-bezier(0.23,1,0.32,1)).
- **Do** marcar conquista em Oliva com sombra oliva (`rgba(168,184,94,.4)`) — treino feito, meta batida, dia completo.
- **Do** usar Mel Torrado para atenção e déficit — informação calorosa, não alarme.
- **Do** gate de hover com `@media(hover:hover) and (pointer:fine)` — o device principal é touch.
- **Do** manter `prefers-reduced-motion`: fade permanece, deslocamento e stagger somem.
- **Do** stagger curto (0.02-0.26s) em listas de cards que entram.

### Don't:
- **Don't** usar vermelho ou tom de erro para dados nutricionais — "app de dieta punitivo" é anti-referência nominal do PRODUCT.md.
- **Don't** adicionar mascotes, confete ou badges decorativos — "infantilizado/gamificado demais" é anti-referência nominal.
- **Don't** usar Anton em texto corrido, botões ou labels — Anton é dado, Manrope é voz.
- **Don't** passar sombra preta de 10% de opacidade — destaque vem de cor e escala, não de drop shadow.
- **Don't** colocar duas cores de destaque competindo no mesmo card (The Uma-Voz-Por-Card Rule).
- **Don't** usar texto Névoa Clara (#BBBBBB) em informação essencial — só metadado descartável.
- **Don't** quebrar o limite de 460px da coluna — o app é uma coluna mobile, sempre.

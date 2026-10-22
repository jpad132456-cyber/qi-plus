# DESIGN.md — QI+

Especificações visuais do site (`index.html`).

Como ler este arquivo: só é regra o que está marcado como **Regra**. O resto descreve como o site está hoje, para consulta. Não é padrão a seguir nem a copiar. Regra nova só entra aqui quando vier do dono do projeto.

---

## 1. Tipografia

### Regra: três tamanhos, por importância

O tamanho da fonte mostra a importância do conteúdo: quanto maior, mais importante. Existem só três tamanhos.

| Tamanho | Valor | Importância | Para quê |
|---|---|---|---|
| **Grande** | `clamp(32px, 4.8vw, 56px)` | Alta | O que a pessoa não pode deixar de ler |
| **Médio** | `17px` | Intermediária | O que explica e sustenta o que é importante |
| **Pequeno** | `13px` | Baixa | Detalhes que só lê quem quiser |

Para escolher o tamanho, pergunte "quão importante é isto?", e não "que tipo de elemento é isto?". Não use outros tamanhos.

### Famílias usadas hoje

Geist (sans) e Geist Mono, carregadas pelo Google Fonts.

### Estado atual

O `index.html` usa cerca de 30 tamanhos diferentes (de 11px a 84px) e ainda não segue a regra.

---

## 2. Cores

### Regra: onde o laranja pode aparecer

O laranja `#ff6a3d` e o gradiente laranja → âmbar (`linear-gradient(100deg, #ff6a3d, #ffb03a)`) só podem aparecer em dois lugares:

1. **No título inicial** da página (o título do hero).
2. **Nos botões que vendem ou levam a uma ação importante.** "Importante" quer dizer: o cliente inserir o cadastro e a venda continuar.

Fora disso, não use laranja em texto nem em botão.

Hoje o site não segue isso: todo `h2` tem um trecho em gradiente (`.gt`), todo eyebrow de seção é laranja, e o laranja também aparece em ícones, bordas, marcadores e brilhos.

### Cores usadas hoje

Descrição do estado atual, não regra.

**Base neutra** (definida em `:root`)

| Token | Hex | Onde aparece | Por quê |
|---|---|---|---|
| `--bg` | `#050507` | Fundo da página, `theme-color`, fundo de inputs | Quase preto com um toque de azul, menos chapado que `#000` |
| `--bg-2` | `#09090d` | Blocos recuados (`.costs`, `.stamp-box`, `.guide`) | Um degrau acima do fundo |
| `--card` | `#0e0e13` | Cards, `.pillars`, `.final`, `.brand` | Superfície que se separa do fundo |
| `--card-2` | `#14141b` | Chips do palco da solução | Segundo degrau de superfície |
| `--line` | `rgba(255,255,255,.08)` | Divisórias internas | Separa sem pesar |
| `--line-2` | `rgba(255,255,255,.15)` | Bordas de componentes e de itens clicáveis | Contorno visível |
| `--fg` | `#f7f7f8` | Títulos e texto principal | Branco levemente suavizado |
| `--muted` | `#b0b0bc` | Parágrafos de apoio | Recua o texto secundário |
| `--dim` | `#777784` | Metadados, placeholders, rodapé | Recua o que é detalhe. Contraste: ~4,6:1 em `--bg`, ~4,4:1 em `--card`, ~4,2:1 em `--card-2` |

**Marca**

| Token | Hex | Onde aparece | Por quê |
|---|---|---|---|
| `--accent` | `#ff6a3d` | Logo, botão primário, eyebrows, nós do fio, foco de input, "+" do FAQ, seleção de texto | Cor do logo |
| `--accent-2` | `#ffb03a` | Segundo ponto do gradiente, contorno de foco do teclado, anéis do logo, ícones, cursor do terminal | Complemento do laranja |
| `--grad` | `linear-gradient(100deg, #ff6a3d, #ffb03a)` | Botão primário, `.gt` nos títulos, barra de progresso, sublinhado do menu | Une as duas cores da marca |
| — | `#0a0a0a` | Texto sobre o laranja e o gradiente (botões, "+" do logo, avatares) | Contraste sobre cor clara |

**Problema × solução**

| Token | Hex | Onde aparece | Por quê |
|---|---|---|---|
| `--bad` | `#ff6b6b` | "✕ Sem padrão", selos "inventado"/"retrabalho", marcadores de custo, erros de formulário | Marca o erro, o mundo sem QI+ |
| `--good` | `#4ade80` | "✓ Com QI+", selos "conforme", critérios aprovados, carimbo "APROVADA" | Marca o que foi verificado |
| — | `#d6c9c9` | Valores da coluna "Sem padrão" no hero | Texto cinza avermelhado |
| — | `#ff4d4d`, `#d93636` | Listras da barra "sem skill" | Variação do vermelho |
| — | `#0d1510`, `#0f1712` | Fundo tingido de verde (coluna "Com QI+", chip aprovado) | Variação do verde |

**Pilares**

| Token | Hex | Pilar |
|---|---|---|
| `--pi` | `#ff6a3d` | Inteligência |
| `--po` | `#ffb03a` | Organização |
| `--pa` | `#4ade80` | Aprimoramento |

**Atmosfera** (orbs desfocadas do fundo, trocadas por seção via `data-atm`)

| Seção | Cores |
|---|---|
| Hero `#topo` | `#ff6a3d`, `#8b6cff` |
| `#problema` | `#ff3b3b`, `#7a1f3d` |
| `#solucao` | `#16a34a`, `#0ea5a0` |
| `#padrao` | `#22c55e`, `#3dd6ff` |
| `#repositorio` | `#0ea5e9`, `#22c55e` |
| `#compatibilidade` | `#8b6cff`, `#3dd6ff` |
| `#como` | `#ff6a3d`, `#8b6cff` |
| `#faq` | `#8b6cff`, `#ff6a3d` |
| `#contato` | `#ff6a3d`, `#ffb03a` |

**Outras**

| Hex | Onde aparece |
|---|---|
| `#ff5a5a` | Início do fio, na região do problema |
| `#5eead4`, `rgba(45,212,191,…)`, `rgba(20,184,166,…)` | Faixa de segurança (`.sec-strip`) |
| `#8b6cff`, `#3dd6ff` | Avatares do chat, sombra do terminal |
| `#2a2a33` | Bolinhas do terminal, avatar "IA" |
| `#e6e6ea` | Texto do terminal |
| `#0c0c11`, `#0b0b10`, `#08080b`, `#111117`, `#0a0a0e` | Superfícies avulsas (`.proof`, `.chat`, `.review`, `.drawer`, `.mnav`, `.term`) |
| `#000` | Texto da seleção e do filtro ativo |

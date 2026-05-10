# Instruções do Projeto

## Quem sou

Economista e consultor especializado em finanças públicas brasileiras. Atendo gestores de ativos e organizações do setor público. Os painéis produzidos aqui são instrumentos analíticos — para reuniões com investidores, apresentações de política pública e briefings técnicos.

---

## Identidade visual (obrigatório seguir em todo painel)

### Paleta de cores
```css
--bg:    #ffffff   /* fundo da página */
--panel: #f7f7f5   /* cards, nav, tabelas */
--ink:   #1a1a1a   /* texto principal */
--muted: #5b5b5b   /* texto secundário, labels */
--accent:#003d6b   /* azul-marinho — cor institucional principal */
--warn:  #b8460e   /* laranja — atenção, risco */
--good:  #1f6e3d   /* verde — positivo */
--bad:   #a4243b   /* vermelho — negativo / alerta grave */
--line:  #d8d8d4   /* bordas e separadores */
--hl:    #fff7d6   /* amarelo suave — callout de destaque */
```

### Tipografia
- Font stack: `-apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
- Tamanho base: 14px, line-height 1.5
- Fórmulas matemáticas: `"Cambria Math", Georgia, serif` em itálico

### Layout padrão
- Grid de duas colunas: `nav (240px) + main (1fr)`
- Nav lateral fixo (sticky), com scroll interno
- Main com `padding: 28px 36px`, `max-width: 1100px`
- Responsivo: abaixo de 800px colapsa para coluna única
- Print: nav oculta, seções exibidas em sequência com quebra de página

---

## Componentes padrão

### KPI cards
```
.kpi-grid — grid auto-fit com mínimo de 180px
.kpi      — fundo panel, borda esquerda 4px accent, border-radius 3px
.kpi.good / .warn / .bad — variantes por cor semântica
```
Estrutura interna: `.label` (11px, uppercase) → `.value` (22px, bold) → `.delta` (11px, muted)

### Tabelas
- Colapso de bordas, width 100%, font-size 13px
- `th`: fundo panel, bold
- `td.num`: alinhado à direita, tabular-nums

### Callout
- Fundo `--hl`, borda esquerda `--warn`, radius 3px
- Usado para avisos e destaques críticos

### Thesis box
- Fundo `#eef4f8`, borda `1px solid --accent`, radius 4px
- Tag em uppercase + parágrafo de tese principal

### Cenários (two-col)
- Grid `1fr 1fr`, gap 18px
- `.scenario`: fundo panel, borda topo accent
- `.scenario.alt`: borda topo warn

### Pills de rating
- `.pill.green`, `.pill.red`, `.pill.bb`, `.pill.ba1`
- Radius 10px, font-size 11px

### Navegação lateral
- `h1`: 13px, accent, letter-spacing 0.5px
- Links: padding 8px 18px, borda esquerda transparente
- Ativo: borda esquerda accent, fundo `#ececea`, bold

---

## Comportamento da navegação (JS padrão)
- Seções com `class="section"`, exibidas via `class="section active"`
- Links com `class="navlink"`, navegação via `history.replaceState`
- Scroll para o topo ao trocar de seção (`behavior: 'instant'`)

---

## Tom e estrutura de conteúdo

- Linguagem direta, analítica, sem adjetivos desnecessários
- Números com unidades sempre explícitas (% GDP, R$ bn, pp)
- Fontes citadas de forma compacta (`.src`, font-size 11px, muted, itálico)
- Seções numeradas no título (`h2`) e no nav
- Última seção sempre: Fontes, Glossário e Notas Metodológicas

---

## Regras de construção

1. **Sempre partir do `template.html`** — nunca de zero
2. Não alterar a paleta de cores sem instrução explícita
3. Não adicionar bibliotecas externas (Chart.js, D3 etc.) sem instrução — usar SVG inline ou CSS puro
4. Manter responsividade e regras de print
5. Comentários HTML em português, no formato `<!-- === SEÇÃO === -->`
6. Se houver logomarca disponível no projeto, inserir no topo da nav em `<img>` com `max-width: 160px`

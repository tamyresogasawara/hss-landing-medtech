# HSS — Health Sync Solutions

Landing page do MedTech Challenge — Fase 1.

## Como rodar

Não precisa de build. Basta abrir o `index.html` no navegador.

```bash
# macOS
open index.html
```

Ou rode um servidor local pra evitar limitações de `file://`:

```bash
# Python 3
python3 -m http.server 8000

# Node (se tiver)
npx serve .
```

Depois acesse `http://localhost:8000`.

## Estrutura

```
hss-landing/
├── index.html               # Estrutura semântica + copy completo
├── styles/
│   ├── reset.css            # Normalização cross-browser
│   ├── variables.css        # Design tokens (cores, fontes, espaçamentos)
│   ├── base.css             # Tipografia e layout primitives
│   └── components.css       # Header, hero, cards, formulário, footer
├── assets/
│   └── images/              # (vazio — usar pra adicionar imagens depois)
└── README.md
```

## Seções da página

1. **Hero** — Proposta de valor + dashboard mockup
2. **Problema** — 3 dores das clínicas
3. **Solução** — 3 pilares: Centralize, Automatize, Otimize
4. **Funcionalidades** — 6 módulos do produto (Recall com IA é o diferencial disruptivo)
5. **Para quem** — 3 personas B2B
6. **Diferenciais** — 4 cards com números (LGPD, 48h setup, suporte 7d, atualizações)
7. **CTA + Formulário de lead** — captura de contato
8. **Footer** — links, redes sociais, copyright

Navegação por âncora funciona em todas as seções (smooth scroll nativo via CSS).

## Identidade visual

Tudo centralizado em `styles/variables.css`. Mexa lá pra mudar tudo de uma vez.

| Token | Valor | Uso |
|-------|-------|-----|
| `--color-primary` | `#0a4d68` | Azul-petróleo, cor principal |
| `--color-accent` | `#5dbea3` | Verde-menta, destaques e CTAs secundários |
| `--color-bg` | `#ffffff` | Branco, base da página |
| `--color-bg-soft` | `#f7fafc` | Fundo de seções alternadas |
| `--font-heading` | Plus Jakarta Sans | Títulos |
| `--font-body` | Inter | Corpo de texto |

## Como editar o copy

Tudo está dentro de `index.html`, comentado por seção (busque por `<!-- ========== HERO ==========`). Cada seção tem:

- **Eyebrow** (`section__eyebrow`) — rótulo curto acima do título
- **Title** (`section__title`) — título principal
- **Subtitle** (`section__subtitle`) — descrição abaixo do título
- **Cards** — variam por seção

## Como adicionar / remover seções

1. Duplicar o bloco `<section class="section">` correspondente em `index.html`
2. Mudar o `id` da seção
3. Adicionar o link no `<nav class="nav">` no header
4. Adicionar o link em `<div class="footer__col">` se quiser que apareça no rodapé

## Responsividade

Mobile-first com breakpoints:
- `1024px` — 4 colunas → 2
- `880px` — multi-coluna → 1 coluna, ativa stack
- `720px` — menu hamburguer ativo
- `480px` — ajustes finais (botões full-width, etc.)

Testado em Chrome, Safari e Firefox.

## JavaScript

Bem mínimo, dentro do próprio HTML:

1. **Toggle do menu mobile** — abre/fecha o menu hamburguer e fecha quando clica num link
2. **Submit do formulário** — valida HTML5 e mostra `alert` (sem backend nessa fase)

Quando for plugar backend de verdade (fase 2+), substituir o handler do form em `index.html`.

## Próximas fases (não cobertas aqui)

- Calculadora de ROI interativa
- Deploy (Vercel, Netlify, GitHub Pages — todos funcionam direto sem build)
- Vídeo-pitch
- Pivot opcional pra Tailwind se a complexidade de estilos crescer

## Critérios de avaliação cobertos

- [x] Clareza na estrutura e hierarquia da informação
- [x] Coerência da identidade visual (paleta health-tech, tipografia moderna)
- [x] Qualidade e organização do conteúdo
- [x] Formulário de captação de lead presente
- [x] Navegação funcional entre seções (anchor links + smooth scroll)
- [x] Solução disruptiva (Recall com IA pra reduzir no-show — número que mais dói em clínica)

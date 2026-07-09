# Conceito 2026 — Home da Prefeitura de Matias Barbosa

Novo conceito visual da página inicial, **substituindo** o layout atual por uma
experiência moderna, acessível e centrada no cidadão. Inspiração: Prefeitura de
Belo Horizonte + PortalFacil + Apple / Airbnb / Material Design 3.

**Arquivo único, autossuficiente:** `index.html` (Bootstrap 5 via CDN + CSS/JS
inline). Abra direto no navegador — nenhuma dependência local além dos SVGs.

## Identidade

- Paleta institucional: **azul** (ação) · **verde** · **amarelo** · **vermelho só em detalhes** · branco predominante · cinzas neutros.
- Faixa de 4 cores + **pictogramas** (prédio/igreja/coreto/ponte) incorporados no hero, seções e rodapé — recriados em SVG.
- Tipografia: Poppins (títulos) + Inter (texto).

## Estrutura da Home

Top bar (acessibilidade/idiomas) → faixa 4 cores → masthead sticky (logo + menu +
busca + Fale Conosco) → **faixa de acesso rápido** (14 ícones roláveis: 2ª Via IPTU,
Consultas Públicas, Licitações, Licença Ambiental, Portal Servidor, NFS-e, Telefones,
Processo Seletivo, Certidão Negativa, Diário Oficial, Protocolo Online, Guia de
Serviços, Contas Públicas, Downloads) → **Hero** (slogan ADM 25/28 + atalhos +
colagem de pictogramas — **sem** campo de busca, que fica só no topo) →
**Serviços mais procurados** (com **abas por categoria**
Cidadão / Empresa / Servidor que trocam o grid de cards) → **Indicadores
municipais** (contadores) → **Notícias** (box `MateriaBox` do PortalFacil: slider
`col-8` + lista estática `col-4` + "Veja mais", no padrão do portal de Colatina) →
**Vídeos + Agenda** → **Telefones úteis** → **Rodapé** (Eu ♥ Matias + colunas + pictogramas).

> A seção de Notícias usa as **classes reais do `MateriaBox`** (`materia-box`,
> `embla`, `materia-box-static-item`, `bt-vejamais`…), estilizadas conforme o
> conceito. No PortalFacil, o slider vira `<MateriaBox display-mode="slider">` e a
> lista `<MateriaBox display-mode="list-static" use-btn-view-more="true">`. No
> preview standalone, um slider vanilla (dots + auto-advance) simula o Embla, e as
> imagens são placeholders em gradiente (as do portal real vêm do CMS).

## Recursos

- Sticky header, microinterações (hover lift, ícones), contadores animados (IntersectionObserver).
- Acessibilidade: skip-links, foco visível, **alto contraste** e **A-/A+** persistentes, idiomas, semântica, `prefers-reduced-motion`.
- Responsivo mobile-first (menu hambúrguer, grids fluidos).

## SUBSTITUIR antes de publicar (assets oficiais)

Os itens abaixo foram **recriados em SVG/placeholder** por eu não ter os arquivos:

| Placeholder atual | Trocar pelo arquivo oficial |
|---|---|
| **`images/logo.svg`** (logo no masthead, agora via `<img>`) | logo OFICIAL da Prefeitura (PNG/SVG) — basta substituir o arquivo |
| **`images/pic-casarao.svg` · `pic-igreja.svg` · `pic-coreto.svg` · `pic-ponte.svg`** (colagem do hero, agora via `<img>`) | pictogramas OFICIAIS da cidade (`Ações-_8_.png` etc.) |
| Selo "Eu ♥ Matias Barbosa" (rodapé) | `Eu-amo-matias-_1_.png` |
| Skyline do hero | `ADM 2025 - PREFEITURA CONTORNO.png` |
| Indicadores, notícias, telefones | dados reais do município |

> **Logo e pictogramas já são `<img>`** — é só trocar os arquivos em `images/`
> (mantendo os nomes) que o layout se atualiza sozinho. O campo de busca do Hero
> foi **removido** (a busca fica no topo, no masthead).

Também: apontar menu/serviços/redes sociais para as URLs reais.

## Adaptar ao PortalFacil (opcional)

Este conceito é um **HTML standalone** (como pedido). Para publicar no PortalFacil,
os blocos dinâmicos (notícias, vídeos, banner, busca, menu) devem virar os Boxes
correspondentes (`MateriaBox`, `YouTubeBox`, `BannerBox`, `BuscaAvancadaBox`,
`MenuPortal`) — o mesmo mapeamento já usado em `../templateMB-gov`.

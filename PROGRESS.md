# CarbonPrint — Progresso do Projeto

## Meta
Publicar site institucional do CarbonPrint em **https://carbonprint.com.br** via GitHub Pages.

## Brand (fonte: Google Pomelli — brandbook.md neste repo)
- Cores: Obsidian `#121316` · Graphite `#4A4E58` · Chartreuse `#84CC16` · Chalk `#F3F4F6`
- Fontes: Saira Semi Condensed (display) · IBM Plex Sans (texto)
- Copy completa do site V2 extraída do Pomelli.

## Checklist
- [x] Acesso ao Pomelli (conta lotanois@gmail.com) e extração do brand book + copy do site gerado
- [x] `gh` CLI instalado e autenticado (FrossiPena)
- [x] Repo clonado, brand book commitado
- [x] PDF do brand book baixado do Pomelli e commitado (brandbook.pdf)
- [x] Site estático construído pelo Claude Code CLI (Opus, claude-opus-4-5): index.html + style.css
- [x] Repo tornado público (Pages exige) + CNAME + GitHub Pages habilitado (build ok, redireciona p/ carbonprint.com.br)
- [x] **BLOQUEIO RESOLVIDO: anuidade paga** — domínio Publicado, válido até 24/09/2027
- [x] DNS configurado via API do painel (freedns-advanced POST/PUT): 4×A `@` → 185.199.108-111.153 + CNAME `www` → frossipena.github.io — confirmado no a.sec.dns.br
- [ ] HTTPS: certificado Let's Encrypt do GitHub em provisionamento; depois `gh api pages -X PUT -F https_enforced=true`
- [ ] Teste final em https://carbonprint.com.br
- Lição: login do registro.br no Chrome de automação expira rápido; a API interna do painel (`/v2/ajax/domain/<dom>/freedns-advanced` com header X-XSRF-TOKEN do cookie) permite editar a zona programaticamente.

## Decisões
- Hospedagem: GitHub Pages (site estático, sem backend)
- Editável direto no repo — o site do Pomelli fica como referência de copy/brand, não como fonte de verdade.
- Pendências com o usuário: dados de acesso ao registro.br (painel do domínio).

## Notas técnicas
- `gh` em `/c/Program Files/GitHub CLI/gh.exe` (winget), git protocolo https.
- IP GitHub Pages: 185.199.108.153 / .109 / .110 / .111; CNAME www → frossipena.github.io.


## Design review (Opus, aplicado)
- Hero 2 colunas desktop, imagem acima do texto no mobile; hamburger funcional (JS inline)
- Grades corrigidas: Serviços 3 col; Valores e Materiais 4→2→1; showcase 3→2→1
- Contraste dos textos cinza melhorado; :focus-visible; prefers-reduced-motion
- A11y/SEO: <main>, skip-link, aria-labels, theme-color, Open Graph, h3 em Specs/Destaques
- width/height nas imagens (evita layout shift); acentos pt-BR revisados

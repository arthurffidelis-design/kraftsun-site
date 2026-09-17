# KraftSun · Site v3 "Campo e mesa" (redesenho aprovado em 16/09/2026)

## O que é
Site novo do www.kraftsun.com.br na direção C ("Campo e mesa"), com a copy e a estrutura do handoff da Ray, HTML/CSS/JS puro (sem bundle do Claude Design).
Google Analytics (G-Y6H7T99HHY) e cabeçalho de SEO mantidos. Pesa ~1,3 MB (contra 3,5 MB do bundle antigo).

## Como subir (GitHub web, repo kraftsun-site)
1. Suba os arquivos deste ZIP na raiz: `index.html` (sobrescreve o atual), `privacidade.html`, `sitemap.xml` e a pasta `assets/` inteira.
2. NÃO apague: og-image.png, favicons, apple-touch-icon.png, robots.txt, agradecimento.html, kratsun2.html, logo-kraftsun.png.
3. Commit. O Render publica sozinho. Se aparecer a versão antiga: Cloudflare › Caching › Purge Everything.
4. Depois: Search Console › inspecionar https://www.kraftsun.com.br/ › solicitar indexação.
5. Se precisar voltar: restaure o `index.html` anterior pelo histórico de commits.

## Antes de publicar (bloco "CONFIGURE AQUI" no fim do index.html)
- `SUPORTE_EMAIL` (suporte@kraftsun.com.br precisa existir no Workspace) e `SUPORTE_WHATSAPP` (o botão só aparece quando preenchido).
- `YOUTUBE_CANAL` (hoje o link do rodapé vai para o vídeo de 1 min).
- Números 2.000+ / 200+ / 14 (a Ray pediu validar).
- Canadian Solar está como texto na esteira. Para a logo: copie `app/static/marcas/csi.png` do portal para `assets/marca-canadian.png` e troque o `<span class="txt">Canadian Solar</span>` por `<img src="assets/marca-canadian.png" alt="Canadian Solar">` (nos dois blocos da esteira).
- Para o endereço curto da política nas lojas: Render › Redirects/Rewrites › `/privacidade` → `/privacidade.html` (Rewrite).

## Telas usadas
- Hero e "O laudo na prática": telas do laudo (versão anterior do produto). Se quiser atualizar, mande prints novos que eu troco.
- "Sua carteira inteira": painel atual (16/09, "Sua carteira está em dia"), recortado e com o nome da conta desfocado: `assets/painel-atual.png`.

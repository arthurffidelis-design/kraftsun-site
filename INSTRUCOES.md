# KraftSun · Site novo (handoff Ray D'Paula, 16/09/2026)

## O que é
Site www.kraftsun.com.br refeito do zero em HTML/CSS/JS puro (sem bundle do Claude Design), seguindo o handoff "Ajustes de copy e estrutura para o site".
Substitui TUDO que está no repositório `arthurffidelis-design/kraftsun-site`.

## Como subir (GitHub web)
1. No repositório `kraftsun-site`, apague os arquivos antigos da raiz (index.html antigo do Claude Design e o que mais estiver lá),
   MENOS: `og-image.png`, `favicon-32x32.png`, `favicon-192x192.png`, `favicon-512x512.png`, `apple-touch-icon.png` (esses continuam sendo usados).
2. Suba os arquivos deste ZIP na raiz: `index.html`, `privacidade.html`, `robots.txt`, `sitemap.xml` e a pasta `assets/`.
3. Commit → o Render (serviço kraftsun-1, publishPath ".") publica sozinho.
4. Opcional, para o endereço curto da política nas lojas de app: Render › kraftsun-1 › Redirects/Rewrites → `/privacidade` → `/privacidade.html` (Rewrite).

## Antes de publicar, confira (marcados no site)
- `SUPORTE_EMAIL` e `SUPORTE_WHATSAPP` no fim do `index.html` (bloco "CONFIGURE AQUI"). O e-mail suporte@kraftsun.com.br precisa existir no Google Workspace.
- `YOUTUBE_CANAL`: endereço do canal (hoje o link vai para o vídeo de 1 min).
- Números de prova social "2.000+ diagnósticos" e "200+ integradores" (Ray pediu validar).
- Logo da Canadian Solar: está como texto. Copie `app/static/marcas/csi.png` do portal para `assets/marca-canadian.png` e troque o `<span class="txt">Canadian Solar</span>` por `<img src="assets/marca-canadian.png" alt="Canadian Solar">`.

## O que mudou (checklist do handoff)
1. Etiqueta do hero: "Diagnóstico técnico para o pós-venda solar". ✔
2. Headline com "Antes da visita". ✔
3. Subheadline de 1 frase. ✔
4. Seção "Você conhece essa rotina" removida; toggle antes/depois assume a dor. ✔
5. Calculadora de ROI logo após o toggle. ✔
6. "O laudo na prática" com print simplificado no celular (só 1 imagem). ✔
7. Rodapé: "Preciso · Seguro · Comprovado". ✔
8. Rodapé com Suporte, Guia de uso, YouTube e Instagram (+ contato). ✔
9. "Fale com o time" com canal real (e-mail; WhatsApp aparece ao preencher o número). ✔
10. FAQ de quem já é cliente (equipe, saída de técnico, cobrança, troca de plano, cancelamento). ✔
11. Testado em viewport 390px e 1360px. ✔
Decisão dos sócios (Helion): a seção "Diagnóstico + monitoramento / Helion App" SAIU. O monitoramento 24h aparece como função do próprio KraftSun (faixa "O diagnóstico é o começo" e nos planos), sem citar o Helion.
Copy atualizada de tabela: 14 fabricantes, cortesia de 1 diagnóstico no cadastro, antes de pagar (confirmado por Arthur em 16/09), pacotes 10/R$50 · 30/R$135 · 50/R$199, monitoramento 20/80/250 usinas, cartão ou Pix.

## Estrutura
- `index.html`: página única, CSS e JS embutidos, fontes Sora + Source Sans 3 (Google Fonts, com fallback).
- `assets/`: logos (azul e branca), telas do produto e marcas dos fabricantes, extraídas do site atual e reduzidas (≈ 1 MB no total contra 3,5 MB do bundle).
- `privacidade.html`: Política de Privacidade (LGPD) para o site, o portal e o app das lojas. Revisar antes de publicar.

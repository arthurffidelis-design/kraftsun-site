# KraftSun Site · pacote SEO (robots, sitemap, cabeçalho, prévia de link e ícones)

Sobe no repositório **kraftsun-site** (o site estático www.kraftsun.com.br, serviço `kraftsun-1` do Render). Não mexe no portal nem no CRM.

## O que estava faltando (conferido em 10/09/2026)

- Não existia `sitemap.xml` em nenhum domínio.
- O `robots.txt` que aparecia era o gerenciado pelo Cloudflare, não um nosso.
- O `index.html` exportado do Claude Design não tinha idioma (`lang`), descrição, canonical, Open Graph (prévia no WhatsApp) nem ícones, e o título era "Kraftsun - Para quem quer ser mais que um vendedor".
- O conteúdo da página só existia depois do JavaScript montar ("Unpacking..."). Sem JavaScript, o Google via só o título.
- Nenhuma das 9 contas Google do seu Chrome tem propriedade no Search Console: o site nunca foi registrado no Google.

## O que este pacote faz

| Arquivo | O que é |
|---|---|
| `index.html` | O mesmo site que está no ar, com três acréscimos: (1) cabeçalho completo, no documento e dentro do template que o empacotador monta: título "KraftSun · Diagnóstico de usinas solares para integradores", descrição, `lang="pt-BR"`, canonical, Open Graph e Twitter Card com imagem, ícones, dados estruturados (Organization, WebSite, SoftwareApplication com os 3 planos); (2) uma versão estática do conteúdo da página (títulos, textos, planos, perguntas frequentes e links) que o Google lê no HTML puro e que aparece para quem está sem JavaScript; ela some no instante em que a página monta, então quem navega não vê diferença; (3) nada mais mudou: o design, o vídeo, a calculadora e o Google Analytics (G-Y6H7T99HHY) continuam iguais |
| `robots.txt` | Libera tudo e aponta o sitemap. O Cloudflare continua colocando o bloco dele (bots de IA bloqueados) na frente; o nosso vale junto |
| `sitemap.xml` | A home (a página é única; as seções são âncoras e não entram em sitemap) com a imagem de prévia |
| `og-image.png` | Prévia de link 1200×630 (WhatsApp, LinkedIn, Instagram DM, Google): logo, a frase principal e "13 fabricantes, sem hardware" |
| `favicon-16x16.png`, `favicon-32x32.png`, `favicon-192x192.png`, `favicon-512x512.png`, `apple-touch-icon.png`, `favicon.ico` | Ícones a partir do símbolo que já estava dentro do site (o `/favicon.ico` hoje responde 404) |

## Como subir (GitHub web)

1. No repositório `kraftsun-site`: **Add file › Upload files**, arraste todos os arquivos desta pasta para a raiz (o `index.html` substitui o atual).
2. Commit: `site · SEO: robots, sitemap, cabeçalho, prévia de link e ícones`.
3. O Render publica sozinho. Conferir: `www.kraftsun.com.br/robots.txt` mostra o nosso bloco no fim, `www.kraftsun.com.br/sitemap.xml` abre, `www.kraftsun.com.br/og-image.png` abre, e a home continua igual.

## Depois de subir: Search Console (10 minutos, eu conduzo pelo seu Chrome)

1. Escolher a conta Google dona da propriedade. Sugestão: **arthur@environenergia.com.br** ou a conta do Workspace do kraftsun.com.br, não uma pessoal.
2. Em search.google.com/search-console, "Adicionar propriedade" › **Domínio** › `kraftsun.com.br`. Isso cobre www, app, crm e cliente de uma vez.
3. O Google mostra um registro TXT. Ele entra no DNS do Cloudflare (zona kraftsun.com.br, tipo TXT, nome `@`). Você aprova, eu preencho.
4. "Verificar". Depois, em Sitemaps, enviar `https://www.kraftsun.com.br/sitemap.xml`, e em Inspeção de URL pedir a indexação da home.
5. Em 2 a 7 dias o Google começa a mostrar impressões e cliques.

## Duas coisas para você decidir (não estão neste pacote)

1. **Copy do site desatualizada em relação ao produto:** o site diz 13 fabricantes (o portal lê 14, falta a Canadian Solar na lista), "2 diagnósticos de cortesia" (no ar são 5 na primeira assinatura e 1 ao criar a conta) e pacotes de 10 por R$ 50 e 50 por R$ 199 (no portal existem Start 10/R$ 50, Master 30/R$ 135 e Pro 50/R$ 199). O texto estático deste pacote repete o que a página mostra, para não dizer uma coisa no HTML e outra na tela. Quando você ajustar no Claude Design, me manda o novo export que eu reaplico o cabeçalho e o texto estático (é um script, leva minutos).
2. **Portal, CRM e Portal do Cliente indexáveis:** hoje o robots do Cloudflare libera app, crm e cliente.kraftsun.com.br. Na próxima versão do portal e do CRM eu coloco `/robots.txt` com `Disallow: /` e `noindex` no base, para o Google indexar só o site. Se preferir resolver sem subir código, dá para criar no Cloudflare uma regra de resposta para `/robots.txt` nesses três hosts.

## Aviso importante sobre novos exports do Claude Design

Toda vez que o site for exportado de novo do Claude Design, o `index.html` novo vem sem este cabeçalho e sem o texto estático. Antes de subir um export novo, me manda o arquivo que eu devolvo com tudo reaplicado. `robots.txt`, `sitemap.xml`, `og-image.png` e os ícones não são afetados.

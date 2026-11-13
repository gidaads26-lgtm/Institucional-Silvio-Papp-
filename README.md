# Site Silvio Papp | Hipnoterapia Clínica

Site de uma página, feito a partir do modelo do site HipnoQuantec (mesmo CSS e JavaScript). A ordem das seções segue: topo, Antes de tudo, Método, Atendimentos, Como funciona, Local, Depoimentos, Sobre, Dúvidas, Fechamento e rodapé.

## Arquivos

- `index.html`: o site inteiro (textos, estilos e scripts).
- `img/`: fotos (`silvio-papp-retrato.jpg` no topo, `silvio-papp-perfil.jpg` em "Quem sou eu", `consultorio-uru.jpg` no local de atendimento).
- `video/`: vídeos de depoimento.
- `og-silviopapp-v2.jpg`: imagem que aparece quando o link é compartilhado no WhatsApp e nas redes (1200×630).
- `robots.txt` e `sitemap.xml`: ajudam o Google a encontrar o site.

## Antes de publicar: o que falta preencher

Procure por `[a preencher` no `index.html`. Hoje faltam:

1. Formação, instituição e ano, abaixo do nome do Silvio.
2. Plataforma do atendimento online (ex.: Google Meet) e abrangência (todo o Brasil, exterior), na pergunta "O atendimento pode ser online?".

Também atualize:

- O link "Ver no mapa" e o endereço do rodapé apontam para a busca do endereço no Google Maps. Se o Silvio tiver perfil no Google Meu Negócio, troque pelo link do perfil (procure por `maps/search` no arquivo; aparece 2 vezes).

## Como editar textos

Abra o `index.html` em qualquer editor (VS Code, por exemplo). Cada seção começa com um comentário, como `<!-- HERO -->` ou `<!-- DÚVIDAS (FAQ) -->`. Troque só o texto entre as tags. Regras de redação: sem "cura", sem promessa de resultado ou de prazo, sem travessão.

## Como trocar fotos

Substitua o arquivo em `img/` mantendo o mesmo nome e proporção (retrato 4:5; consultório 16:10). Fotos até ~200 KB. Se mudar o tamanho, atualize `width` e `height` na tag `<img>`.

## WhatsApp

Número e mensagem ficam no fim do arquivo, na constante `WHATSAPP` e em `waMsg`. O script reescreve todos os botões marcados com `data-wa`. Um botão com `data-wa-msg="..."` usa a própria mensagem (é o caso de "Perguntar no WhatsApp", nas Dúvidas).

## Depoimentos

A seção `#depoimentos` tem um vídeo próprio (`video/depoimento-1.mp4`, capa em `img/depoimento-1.jpg` e `img/depoimento-1-poster.jpg`). O vídeo abre numa janela e toca direto do site, sem YouTube. Só publique vídeos com autorização por escrito de uso de imagem e voz, e guarde o documento.

Para acrescentar outro vídeo: coloque o MP4 em `video/` (vertical, de preferência até ~5 MB), uma capa 250×350 em `img/` e copie o bloco `<figure class="vitem">` mudando `data-src`, `data-poster`, a imagem e o `aria-label`.

Para um vídeo do YouTube, troque `data-src` por `data-id="CODIGO_DO_VIDEO"`: o site abre o player do YouTube na mesma janela.

## Publicar (Vercel)

1. Crie um repositório no GitHub com estes arquivos na raiz.
2. Na Vercel, "Add New Project", escolha o repositório e publique (sem configuração de build).
3. O domínio provisório usado nas metatags é `https://institucionalsilviopapphipnologo.vercel.app`. Se o endereço final for outro, troque em `index.html` (metatags, `canonical` e JSON-LD), `robots.txt` e `sitemap.xml`.
4. Teste a prévia em https://developers.facebook.com/tools/debug/ (botão "Extrair novamente") e envie o link no WhatsApp com `?v=1` no fim para escapar do cache.

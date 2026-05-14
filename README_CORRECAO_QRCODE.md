# Correção QR Code + Upload Mobile

Arquivos corrigidos:

- `index.html`
- `mobile-upload.html`

## O que foi corrigido

1. O QR Code agora tem fallback visual por imagem.
   - Se a biblioteca local `QRCode` falhar, o app mostra o QR Code usando imagem gerada por URL.
   - O link continua disponível para copiar e abrir diretamente.

2. O `mobile-upload.html` deixou de usar `.single()` na consulta do token.
   - Isso evita o erro: `Cannot coerce the result to a single JSON object`.
   - Agora ele busca o token mais recente e retorna uma mensagem mais clara caso não encontre.

## O que subir no GitHub

Suba/substitua estes arquivos na raiz do repositório:

- `index.html`
- `mobile-upload.html`

Depois aguarde o Cloudflare Pages gerar novo deploy.

## Teste

1. Abra o app no Cloudflare.
2. Pressione `Ctrl + F5`.
3. Gere um QR Code.
4. O QR deve aparecer visualmente.
5. Clique em `Abrir upload`.
6. A tela mobile deve abrir com o contexto do token.

Se abrir `/mobile-upload.html` sem token, é normal aparecer erro de token ausente/inválido.

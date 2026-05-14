# Atualização: exclusão de devolução + QR Code de evidências

Arquivos desta versão:

- `index.html` — aplicativo principal.
- `mobile-upload.html` — tela aberta pelo celular ao escanear o QR Code.
- `supabase_setup.sql` — atualização do Supabase com tabela de tokens QR e campos de evidências.

## Como atualizar no GitHub

1. Abra seu repositório no GitHub.
2. Substitua ou envie estes arquivos:
   - `index.html`
   - `mobile-upload.html`
3. Faça commit na branch conectada ao Cloudflare Pages, normalmente `main`.
4. Aguarde o Cloudflare fazer o deploy automático.

## Como atualizar o Supabase

1. Entre no Supabase.
2. Abra o projeto do app.
3. Vá em **SQL Editor**.
4. Cole e execute o conteúdo de `supabase_setup.sql`.
5. Verifique se existem:
   - tabela `app_state`;
   - tabela `evidence_files`;
   - tabela `qr_upload_tokens`;
   - bucket `evidencias`.

## Como testar QR Code

1. Abra o app publicado pelo Cloudflare.
2. Abra uma devolução.
3. Clique em **Enviar pelo celular via QR Code**.
4. Escaneie o QR Code com o celular.
5. A tela `mobile-upload.html` será aberta.
6. Tire uma foto ou selecione arquivo.
7. Clique em **Enviar evidência**.
8. Volte ao computador e aguarde alguns segundos.
9. A evidência deve aparecer na Central de Evidências e no contexto vinculado.

## Como testar exclusão

1. Entre com usuário Administrador ou Supervisor.
2. Vá em **Devoluções**.
3. Clique em **Excluir**.
4. Escolha exclusão lógica.
5. Informe motivo obrigatório.
6. Confirme.
7. A devolução será removida da visão operacional, mas ficará disponível em **Devoluções excluídas**.

## Observações importantes

- A exclusão lógica é a recomendada.
- A exclusão definitiva é restrita ao Administrador.
- Evidências são preservadas por padrão.
- O QR Code expira em 15 minutos.
- O bucket `evidencias` está público para o MVP. Em produção, recomenda-se migrar para bucket privado com URLs assinadas e autenticação real.

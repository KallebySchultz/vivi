# 💕 Vivi

Site de amor hospedado no GitHub Pages.

## Configuração do UPLOAD_TOKEN (obrigatório para salvar memórias)

Para que qualquer pessoa que acesse o site possa **adicionar e ver memórias**, você precisa configurar um Personal Access Token (PAT) do GitHub como segredo no repositório. Isso permite que o site salve fotos e textos diretamente no repositório.

### Passo a passo

#### 1. Criar o token no GitHub

1. Acesse [github.com/settings/tokens](https://github.com/settings/tokens)
2. Clique em **"Fine-grained tokens"** → **"Generate new token"**
3. Preencha:
   - **Token name:** `vivi-upload` (ou qualquer nome)
   - **Expiration:** escolha o prazo desejado (ex: 1 ano)
   - **Repository access:** selecione **"Only select repositories"** → escolha `vivi`
4. Em **"Permissions"**, expanda **"Repository permissions"** e defina:
   - **Contents:** `Read and write`
5. Clique em **"Generate token"** e **copie o valor** (começa com `github_pat_...`)

#### 2. Adicionar o token como segredo no repositório

1. Acesse **Settings → Secrets and variables → Actions** neste repositório
2. Clique em **"New repository secret"**
3. Preencha:
   - **Name:** `UPLOAD_TOKEN`
   - **Secret:** cole o token copiado no passo anterior
4. Clique em **"Add secret"**

#### 3. Re-implantar o site

1. Vá em **Actions → Deploy to GitHub Pages**
2. Clique em **"Run workflow"** → **"Run workflow"**
3. Aguarde o deploy concluir

Após isso, qualquer pessoa que acessar `https://kallebyschultz.github.io/vivi/` poderá adicionar memórias que serão salvas no repositório e visíveis para todos.

---

> **Segurança:** o token fica embutido no HTML do site (que é público). Por isso, crie um token com permissão **somente neste repositório** e **somente Contents: Read & Write** para limitar o acesso.

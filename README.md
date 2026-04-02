# 💕 Vivi

Site de amor hospedado no GitHub Pages.

## Configuração (obrigatório para salvar memórias)

O site precisa de apenas **um segredo** configurado no repositório: o `UPLOAD_TOKEN`.

As imagens são salvas diretamente neste repositório (pasta `uploads/`) via GitHub API, sem nenhum serviço externo.

---

### Passo 1 — Criar o token no GitHub

1. Acesse [github.com/settings/tokens](https://github.com/settings/tokens)
2. Clique em **"Fine-grained tokens"** → **"Generate new token"**
3. Preencha:
   - **Token name:** `vivi-upload` (ou qualquer nome)
   - **Expiration:** escolha o prazo desejado (ex: 1 ano)
   - **Repository access:** selecione **"Only select repositories"** → escolha `vivi`
4. Em **"Permissions"**, expanda **"Repository permissions"** e defina:
   - **Contents:** `Read and write`
5. Clique em **"Generate token"** e **copie o valor** (começa com `github_pat_...`)

---

### Passo 2 — Adicionar o token como segredo no repositório

1. Acesse **Settings → Secrets and variables → Actions** neste repositório
2. Clique em **"New repository secret"**
3. Preencha:
   - **Name:** `UPLOAD_TOKEN`
   - **Secret:** cole o token copiado no passo anterior
4. Clique em **"Add secret"**

---

### Passo 3 — Re-implantar o site

Após configurar o segredo:

1. Vá em **Actions → Deploy to GitHub Pages**
2. Clique em **"Run workflow"** → **"Run workflow"**
3. Aguarde o deploy concluir

Após isso, qualquer pessoa que acessar `https://kallebyschultz.github.io/vivi/` poderá adicionar memórias com fotos que serão visíveis para todos.

---

> **Segurança:** o `UPLOAD_TOKEN` fica embutido no HTML do site (que é público). Por isso, crie-o com permissão **somente neste repositório** e **somente Contents: Read & Write**, para limitar o impacto caso alguém extraia o token.

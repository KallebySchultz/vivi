# 💕 Vivi

Site de amor hospedado no GitHub Pages.

## Configuração (obrigatório para salvar memórias)

O site precisa de dois grupos de segredos configurados no repositório:

| Segredo | Para quê |
|---------|----------|
| `UPLOAD_TOKEN` | Salvar metadados das memórias (título, data, texto) no `registros.json` do GitHub |
| `CLOUDINARY_CLOUD_NAME` | Nome da sua conta no Cloudinary (armazenamento das fotos) |
| `CLOUDINARY_PRESET` | Nome do upload preset não autenticado (unsigned) do Cloudinary |

---

### Parte 1 — Configurar o Cloudinary (armazenamento de imagens)

As fotos são enviadas diretamente ao Cloudinary, sem precisar de token secreto em cada upload.

#### 1. Criar conta gratuita

Acesse [cloudinary.com](https://cloudinary.com) e crie uma conta gratuita (plano Free suporta 25 créditos/mês, mais do que suficiente para uso pessoal).

#### 2. Anotar o Cloud Name

No dashboard do Cloudinary, o **Cloud Name** aparece no canto superior esquerdo (ex: `meu-cloud`).

#### 3. Criar um Upload Preset não autenticado

1. Vá em **Settings → Upload → Upload presets**
2. Clique em **"Add upload preset"**
3. Configure:
   - **Preset name:** `vivi_unsigned` (ou qualquer nome)
   - **Signing mode:** `Unsigned`
4. Em **"Upload restrictions"** (opcional), defina `Allowed formats: jpg, jpeg, png, webp` para segurança
5. Clique em **Save**

#### 4. Adicionar os segredos no repositório

1. Acesse **Settings → Secrets and variables → Actions** neste repositório
2. Crie dois segredos:
   - **Name:** `CLOUDINARY_CLOUD_NAME` → **Value:** seu Cloud Name (ex: `meu-cloud`)
   - **Name:** `CLOUDINARY_PRESET` → **Value:** nome do preset (ex: `vivi_unsigned`)

---

### Parte 2 — Configurar o UPLOAD_TOKEN (salvar metadados no GitHub)

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

---

### Parte 3 — Re-implantar o site

Após configurar todos os segredos:

1. Vá em **Actions → Deploy to GitHub Pages**
2. Clique em **"Run workflow"** → **"Run workflow"**
3. Aguarde o deploy concluir

Após isso, qualquer pessoa que acessar `https://kallebyschultz.github.io/vivi/` poderá adicionar memórias com fotos que serão visíveis para todos.

---

> **Segurança:** o `UPLOAD_TOKEN` fica embutido no HTML do site (que é público). Por isso, crie-o com permissão **somente neste repositório** e **somente Contents: Read & Write**. O `CLOUDINARY_CLOUD_NAME` e `CLOUDINARY_PRESET` também ficam no HTML, mas são valores projetados para ser públicos pelo Cloudinary (o upload preset unsigned já controla as permissões do lado do Cloudinary).

# 💕 Vivi — Um Cantinho do Nosso Amor

> *"O amor não se explica, ele se sente. E aqui, a gente sente cada detalhe."* 🌹

---

## O que é isso? 🥺

**Vivi** é um site feito com muito amor, carinho e uns tantinhos de código — criado especialmente para celebrar e eternizar os momentos mais lindos de um casal. 💑

É um espaço só nosso, onde as memórias não se perdem: fotos, sorrisos, aventuras e qualquer recordação especial ficam guardados aqui para sempre, como um diário digital do nosso amor. 📖✨

Cada foto adicionada conta um pedacinho da nossa história. Cada memória registrada é uma prova de que o amor é feito de pequenos momentos que a gente nunca quer esquecer. 🌸

---

## O que tem de especial? 💖

- 🖼️ **Galeria de memórias** — adicione fotos e momentos especiais que ficam visíveis para o casal
- 💌 **Mensagens de amor** — um espaço para eternizar palavras que aquecem o coração
- 🌸 **Design feito com carinho** — corações flutuantes, cores rosadas e toda a energia do amor
- ☁️ **Sempre disponível** — hospedado no GitHub Pages, acessível de qualquer lugar, a qualquer hora
- 🔒 **Seguro e privado** — as memórias são salvas direto no repositório, sem serviços externos

---

## Como acessar? 💻

Basta entrar em: **[https://kallebyschultz.github.io/vivi/](https://kallebyschultz.github.io/vivi/)** 🌐

E deixar o amor falar mais alto. 💗

---

## Configuração (para salvar memórias com fotos) 🔧

Para que o envio de fotos funcione, é necessário configurar **um único segredo** no repositório: o `UPLOAD_TOKEN`.

As imagens são salvas diretamente neste repositório (pasta `uploads/`) via GitHub API — sem nenhum serviço externo. Simples e bonito, assim como o amor. 🌷

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

### Passo 2 — Adicionar o token como segredo no repositório

1. Acesse **Settings → Secrets and variables → Actions** neste repositório
2. Clique em **"New repository secret"**
3. Preencha:
   - **Name:** `UPLOAD_TOKEN`
   - **Secret:** cole o token copiado no passo anterior
4. Clique em **"Add secret"**

### Passo 3 — Re-implantar o site

Após configurar o segredo:

1. Vá em **Actions → Deploy to GitHub Pages**
2. Clique em **"Run workflow"** → **"Run workflow"**
3. Aguarde o deploy concluir ☕

Pronto! Agora qualquer memória adicionada ficará salva e visível para sempre. 🫶

---

> **Segurança:** o `UPLOAD_TOKEN` fica embutido no HTML do site (que é público). Por isso, crie-o com permissão **somente neste repositório** e **somente Contents: Read & Write**, para limitar o impacto caso alguém extraia o token.

---

<div align="center">

Feito com ❤️ e muito amor — para durar para sempre.

*"Eu te amo hoje, amanhã e sempre."* 🌙

</div>

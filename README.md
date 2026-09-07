# Blog NullPointer-9

Blog pessoal construído com [Astro](https://astro.build), publicado de graça no GitHub Pages.

URL publicada: **https://vrcardoso.com.br**

## Recursos

- ✅ Blog em Markdown/MDX com Content Collections (validação de schema)
- ✅ Feed RSS em `/rss.xml`
- ✅ Sitemap automático
- ✅ SEO: URLs canônicas e Open Graph
- ✅ Deploy automático via GitHub Actions
- ✅ Zero JavaScript no navegador (site estático super rápido)

## Requisitos

- Node.js 22.12+
- Conta no GitHub

## Rodando localmente

```sh
npm install
npm run dev
```

O dev server ajuda com o comando `astro dev` (veja `AGENTS.md` para o modo background).

## Publicando no GitHub Pages

1. Crie um repositório **público** (requisito do plano gratuito) chamado `blog` no GitHub:
   `https://github.com/NullPointer-9/blog`.

   > GitHub Pages no plano gratuito só é exibido para o público. Se precisar de um repositório
   > privado, você precisará de um plano pago ou de outra hospedagem.

2. Suba o código:

   ```sh
   git init
   git add .
   git commit -m "feat: blog astro inicial"
   git branch -M main
   git remote add origin https://github.com/NullPointer-9/blog.git
   git push -u origin main
   ```

3. No GitHub, vá em **Settings → Pages** e em **Build and deployment** selecione **GitHub Actions**
   (o workflow `.github/workflows/deploy.yml` faz todo o resto).

4. Aguarde a Action terminar. O site estará no GitHub Pages em `https://nullpointer-9.github.io/blog/`.

## Domínio próprio: vrcardoso.com.br

O projeto já está pronto para servir em `https://vrcardoso.com.br`:

- `public/CNAME` contém `vrcardoso.com.br`
- `astro.config.mjs` usa `site: 'https://vrcardoso.com.br'` (sem `base`)

No Registro.br, aponte o domínio (registros **A**) para os IPs do GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Depois, em **Settings → Pages**, coloque `vrcardoso.com.br` no campo **Custom domain** e salve. O GitHub valida e emite o certificado TLS automaticamente.

## Escrevendo um post

Crie um arquivo em `src/content/blog/` (`.md` ou `.mdx`):

```md
---
title: 'Título do post'
description: 'Resumo exibido na listagem.'
pubDate: 'Sep 07 2026'
heroImage: '../../assets/minha-imagem.jpg' # opcional
---
```

Faça o commit e push — o deploy acontece sozinho.

## Estrutura do projeto

```text
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   ├── content/
│   ├── layouts/
│   └── pages/
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## Documentação útil

- [Astro Guides](https://docs.astro.build)
- [Roteamento no Astro](https://docs.astro.build/en/guides/routing/)
- [Content Collections](https://docs.astro.build/en/guides/content-collections/)
- [Deploy no GitHub Pages](https://docs.astro.build/en/guides/deploy/github/)
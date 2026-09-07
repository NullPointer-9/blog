# Blog NullPointer-9

Blog pessoal construído com [Astro](https://astro.build), publicado de graça no GitHub Pages.

URL publicada: **https://nullpointer-9.github.io/blog/**

## Recursos

- ✅ Blog em Markdown/MDX com Content Collections (validação de schema)
- ✅ Feed RSS em `/blog/rss.xml`
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

4. Aguarde a Action terminar. O site estará em:
   `https://nullpointer-9.github.io/blog/`

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

## Usando um domínio próprio (futuro)

Se um dia apontar um domínio próprio para o GitHub Pages:

1. Atualize `site` no `astro.config.mjs` para `https://seu-dominio.com`.
2. Remova o `base: '/blog'` do `astro.config.mjs`.
3. Ajuste os links internos que usam `import.meta.env.BASE_URL` para retirar o prefixo.
4. Configure o domínio em **Settings → Pages** e o CNAME. Consulte
   [como configurar um domínio personalizado no GitHub Pages](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site).

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
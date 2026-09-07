---
title: 'Como este blog foi construído'
description: 'Astro + GitHub Pages: como este blog foi montado do zero.'
pubDate: 'Jul 15 2022'
heroImage: '../../assets/blog-placeholder-4.jpg'
---

Neste post vou contar como este blog foi construído. A ideia era algo simples, barato e fácil de
manter, tudo versionado no GitHub.

## A stack

O blog usa três peças principais:

- **[Astro](https://astro.build)**: gerador de sites estáticos. Ele converte os posts em Markdown em
  HTML puro, o que deixa o site rápido.
- **GitHub Pages**: hospedagem estática gratuita.
- **GitHub Actions**: o pipeline que compila o site e faz o deploy a cada push.

## Como funciona o deploy

Quando o código chega no branch `main`, o workflow `.github/workflows/deploy.yml` roda automaticamente:

1. Instala as dependências com `npm ci`.
2. Gera o site com `npm run build` (a saída vai para `dist/`).
3. Envia a pasta `dist/` como artefato do GitHub Pages.
4. Publica o artefato no endereço do site.

Como o repositório se chama `blog`, o site fica disponível em:

```
https://nullpointer-9.github.io/blog/
```

## Detalhe importante: o base path

Como o site vive em um subcaminho (`/blog/`), o Astro precisa saber disso. No
`astro.config.mjs` configuramos:

```js
site: 'https://nullpointer-9.github.io',
base: '/blog',
```

E todos os links internos do site usam `import.meta.env.BASE_URL` como prefixo, assim continuam
funcionando mesmo mudando o endereço no futuro.
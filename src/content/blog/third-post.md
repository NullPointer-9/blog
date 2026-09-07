---
title: 'Por que Astro?'
description: 'Algumas razões pelas quais escolhi o Astro para este blog.'
pubDate: 'Jul 22 2022'
heroImage: '../../assets/blog-placeholder-2.jpg'
---

Existem muitos geradores de site estático por aí: Jekyll, Hugo, Eleventy... Então por que o Astro?

## Zero JavaScript no navegador

O Astro entrega HTML, CSS e, se você não pedir, nenhum JavaScript. Para um blog, isso significa que
as páginas carregam quase instantaneamente, sem precisar de um framework inteiro no navegador para
renderizar texto.

## Conteúdo em Markdown no formato certo

Escrever um post é só criar um arquivo `.md` com alguns metadados no topo e o conteúdo em Markdown.
Nada de bancos de dados, painéis administrativos ou complicação.

## Content Collections

O Astro tem um sistema de coleções de conteúdo com validação de schema. Isso garante que todos os
posts tenham os campos obrigatórios (título, descrição, data) — erro de post sem data simplesmente
não compila.

## Recursos prontos

O template já vem com:

- **RSS feed** em `/blog/rss.xml`
- **Sitemap** para ajudar no SEO
- **SEO**: URLs canônicas e Open Graph
- **Suporte a MDX** para quando quiser componentes dentro dos posts

## Deploy barato (de graça)

Com o GitHub Pages o custo é zero e o deploy é um push no `main`. Perfeito para um blog pessoal.
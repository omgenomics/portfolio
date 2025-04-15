# Portfolio Template

A simple template for a portfolio website, with support for writing blogs in Markdown with code highlighting.

## Getting Started

Create a copy of this repo by clicking `Use this template`, then clone your repo:

```bash
git clone https://github.com/YOUR_USERNAME/portfolio.git
npm install
npm run dev
```

## Modifying the template

The main files to modify are:

- Configuration: [src/lib/config.js](./src/lib/config.js) - name, social media links, and navbar links
- Home page: [src/routes/+page.svelte](./src/routes/+page.svelte) - about you, and highlighted projects
- Resume: [src/routes/resume/+page.svelte](./src/routes/resume/+page.svelte) - work experiences and education
- Articles: [src/routes/articles/+page.svelte](./src/routes/articles/+page.svelte)
- Talks: [src/routes/talks/+page.svelte](./src/routes/talks/+page.svelte)

## Markdown posts

To create a blog post at the url `/some/made/up/route/some-topic`, create the file `src/routes/some/made/up/route/some-topic/+page.md` (note the `.md` extension)

Specify the title and date at the top of the file:

```
---
title: How to install the bioinformatics tool XYZ
date: "June 10 2024"
---
```

Use Markdown to write your post, and use "```" around code blocks. To get syntax highlighting on your website, specify the language when you start the block:

````
```bash
echo $myVariable
```

```python
import pandas as pd
```

```R
abc <- c(1, 2, 3)
```
````

- See `src/routes/articles/install-xyz/+page.md` as an example.
- See `src/components/BlogPost.svelte` to change the template for Markdown articles.

## Adding and deleting pages

- Add a new page by creating a file `src/routes/newpage/+page.svelte` and using the pages above as templates to get you started. Then add `newpage` to `NAVBAR_CATEGORIES` in the file `src/lib/config.js`.
- To remove a page, delete the folder `src/routes/oldpage` and remove `oldpage` from the file `src/lib/config.js`.

## Deploy your website

- Create a [Cloudflare](https://cloudflare.com) account
- Under `Compute`, click `Workers & Pages`, `Pages`, then `Connect to git`
- Connect your repo and select the `main` branch. Now every time you push code to that branch, your changes will be automatically deployed!
- Under Build Settings:
  - Framework preset: SvelteKit
  - Build command: `npm run build`
  - Build output directory: `.svelte-kit/cloudflare`

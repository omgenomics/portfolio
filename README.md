# portfolio-template

Template for building your own portfolio website.

## Getting Started

Clone this repo on your computer:

```bash
git clone https://github.com/omgenomics/portfolio.git
npm install
npm run dev
```

## Modifying the template

The main files to modify are:

- Configuration: [src/lib/config.js](./src/lib/config.js)
- Home page: [src/routes/+page.svelte](./src/routes/+page.svelte)
- Resume: [src/routes/resume/+page.svelte](./src/routes/resume/+page.svelte)
- Articles: [src/routes/articles/+page.svelte](./src/routes/articles/+page.svelte)
- Talks: [src/routes/talks/+page.svelte](./src/routes/talks/+page.svelte)

You can add a new page by creating a file `src/routes/newpage/+page.svelte` and using the pages above as templates to get you started. Then add `newpage` to `NAVBAR_CATEGORIES` in the file `src/lib/config.js`

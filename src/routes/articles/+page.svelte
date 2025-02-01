<script>
import { ListGroup } from "@sveltestrap/sveltestrap";
import Article from "$components/Article.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
</script>

<SectionHeader title="Articles" />

<ListGroup flush>
	<Article
		title="How to install the bioinformatics tool XYZ on Mac OS"
		venue="My blog"
		date="June 2024"
		emoji="🧑‍💻"
		url="/articles/install-xyz"
	/>

	<Article
		title="Single-cell RNA sequencing of 1 trillion cells reveals much heterogeneity"
		date="January 2023"
		venue="Nature Science Cell"
		emoji="🧬"
		url="https://google.com"
	/>
</ListGroup>

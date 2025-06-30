<script>
import { ListGroup } from "@sveltestrap/sveltestrap";
import Article from "$components/Article.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
</script>

<SectionHeader title="Talks" />

<ListGroup flush>
	<Article title="My experience debugging..." venue="DebugBioConf" date="June 2024" emoji="🧑‍💻" url="https://google.com" />
</ListGroup>

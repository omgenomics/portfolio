<script>
import Experience from "$components/Experience.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
import { ListGroup } from "@sveltestrap/sveltestrap";
</script>

<SectionHeader title="Work Experience" />

<ListGroup flush>
	<Experience start="January 2 2023" end="March 15 2024" company="Corp" url="https://google.com" />
	<Experience start="January 1 2021" end="Jan 1 2023" company="Yes" url="https://google.com" />
</ListGroup>

<SectionHeader title="Education" />

<ListGroup flush>
	<!-- TBD -->
</ListGroup>

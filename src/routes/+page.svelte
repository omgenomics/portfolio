<script>
import { Row } from "@sveltestrap/sveltestrap";
import ProjectCard from "$components/ProjectCard.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
</script>

<div class="d-flex bg-light p-4 fs-5 rounded-3 border border-2 border-primary-subtle">
	<div class="align-middle pe-3">
		<img height="60" src="/assets/headshot.jpg" alt="That's me :)" />
	</div>
	<div>
		Bioinformatics Scientist at <a href="https://google.com" target="_blank">ABC Bio</a>
		<p class="small text-muted mb-0">A short summary of what you specialize in.</p>
	</div>
</div>

<SectionHeader title="Featured Projects" />

<Row cols={{ xl: 3, lg: 3, md: 2, sm: 1, xs: 1 }}>
	<ProjectCard
		name="🗣️ Talk at BioConf 2024"
		date="Nov 2024"
		url="https://google.com"
		img="TODO"
		description="Spoke about spatial transcriptomics"
	/>

	<ProjectCard
		name="📝 Our XYZ paper has been published"
		date="December 2023"
		url="https://google.com"
		img="/"
		description="We present XYZ, a new tool for something or other"
	/>
</Row>

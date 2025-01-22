<script>
import { Row } from "sveltestrap";
import ProjectCard from "$components/ProjectCard.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
import { CARD_ROWS } from "$lib/config";
</script>

<div class="d-flex bg-light p-4 fs-5 rounded-3 border border-2 border-primary-subtle">
	<div class="align-middle pe-3">
		<img height="60" class="rounded-circle" src="/" alt="That's me :)" />
	</div>
	<div>
		Bioinformatics scientist at <a href="https://google.com" target="_blank">XYZ Biotech</a>
		<p class="small text-muted mb-0">
			I design algorithms for using spatial transcriptomics to detect XYZ.
		</p>
	</div>
</div>

<SectionHeader title="Featured Projects" />

<Row cols={CARD_ROWS}>
	<ProjectCard
		name="🗣️ Talk at BioXYZ Conf 2024"
		date="June 2024"
		url="https://google.com"
		img="/"
		description="Description"
	/>
	<ProjectCard
		name="🗒️ Our tool XYZ is published"
		date="December 2023"
		url="https://google.com"
		img="/"
		description="Description"
	/>
</Row>

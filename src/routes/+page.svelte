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

<SectionHeader title="What's New" />

<Row cols={{ xl: 3, lg: 3, md: 2, sm: 1, xs: 1 }}>
	<!-- Photo by <a href="https://unsplash.com/@xteemu">Teemu Paananen</a> on <a href="https://unsplash.com/photos/pic-bzdhc5b3Bxs">Unsplash</a> -->
	<ProjectCard
		name="📝 Installing XYZ on Apple M1"
		date="April 2025"
		url="/articles/install-xyz"
		img="/assets/talk.jpg"
		description="How to install the XYZ tool on the M1 chips and avoid the error..."
	/>

	<!-- Photo by <a href="https://unsplash.com/@chuttersnap">CHUTTERSNAP</a> on <a href="https://unsplash.com/photos/pic-UmncJq4KPcA">Unsplash</a> -->
	<ProjectCard
		name="🗞️ Our XYZ paper has been published"
		date="December 2024"
		url="https://google.com"
		img="/assets/plants.jpg"
		description="We assembled the Rainbow eucalyptus genome and identified a novel..."
	/>
</Row>

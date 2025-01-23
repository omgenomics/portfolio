<script>
import Experience from "$components/Experience.svelte";
import SectionHeader from "$components/SectionHeader.svelte";
import { ListGroup } from "@sveltestrap/sveltestrap";
</script>

<SectionHeader title="Work Experience" />

<ListGroup flush>
	<Experience start="April 2022" company="ABC Bio" url="https://google.com">
		<ul class="timeline">
			<li>
				<div class="fw-bold">
					Senior Bioinformatics Scientist <span class="fw-normal text-muted small">(Jan 2024 &mdash;)</span>
				</div>
				Led effort to reduce variant calling error rates by 20% in our ABC pipeline, ...
			</li>
			<li>
				<div class="fw-bold">
					Bioinformatics Scientist <span class="fw-normal text-muted small">(Apr 2022 - Jan 2024)</span>
				</div>
				Developed variant calling algorithm for new assay ABC...
			</li>
		</ul>
	</Experience>
	<Experience start="January 2017" end="March 2022" company="XYZ Bio" url="https://google.com"></Experience>
</ListGroup>

<SectionHeader title="Education" />

<ListGroup flush>
	<Experience start="April 2013" end="January 2017" company="ABC Bio" url="https://google.com" />
</ListGroup>

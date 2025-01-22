<script>
import { Card, Col } from "@sveltestrap/sveltestrap";

export let name;
export let date = null;
export let description = "";
export let url;
export let img;
</script>

<Col>
	<Card color="light" body class="shadow-lg mt-3">
		<h5>
			<a class="text-decoration-none stretched-link" href={url} target="_blank">
				{name}
			</a>
		</h5>
		<p class="fw-light text-muted">
			{description}
			{#if date}
				<br />
				<small class="opacity-75">
					{date}
				</small>
			{/if}
		</p>
		<img height="300" class="object-fit-cover" src={img} alt="{name} screenshot" />
	</Card>
</Col>

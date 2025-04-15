<script>
import { Card, Col } from "@sveltestrap/sveltestrap";

let { name, date = null, description = "", url, img } = $props();
</script>

<Col>
	<Card color="light" body class="shadow-lg mt-3">
		<h5>
			<a class="text-decoration-none stretched-link" href={url} target={url.startsWith("/") ? "" : "_blank"}>
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
		{#if img}
			<img height="300" class="object-fit-cover" src={img} alt="{name} screenshot" />
		{/if}
	</Card>
</Col>

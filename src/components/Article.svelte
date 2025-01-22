<script>
import { ListGroupItem } from "@sveltestrap/sveltestrap";
let { url, title, description = null, date, venue = null, emoji = "📄", author = null } = $props();
</script>

<ListGroupItem class="p-0 pt-3">
	<span class="fs-5">
		{emoji}
		<a class="text-decoration-none" href={url} target="_blank">
			{title}
		</a>
		<p class="small text-muted">
			{#if description}
				<span class="text-dark">{@html description}</span><br />
			{/if}
			{date}
			{#if venue}
				&bullet;
				<span class="fw-bold">
					{venue}
				</span>
			{/if}
			{#if author}
				<br />
				<span class="small text-muted">
					<small>
						by <strong>{author}</strong>
					</small>
				</span>
			{/if}
		</p>
	</span>
</ListGroupItem>

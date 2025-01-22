<script>
import { ListGroupItem } from "@sveltestrap/sveltestrap";
import { format, formatDistanceStrict } from "date-fns";

export let start = "January 1 1970";
export let end = null;
export let company = null;
export let url = null;
export let image = null;

$: startDate = new Date(start);
$: endDate = end ? new Date(end) : new Date();
$: nbYears = formatDistanceStrict(startDate, endDate);
</script>

<ListGroupItem class="p-0 mt-2">
	<h5 class="mt-1 mb-1">
		{#if image}
			<img class="me-1" width="35" height="35" src={image} alt="Logo for {company}" />
		{/if}
		<a class="text-decoration-none" href={url} target={!url ? null : "_blank"}> {company} </a>
	</h5>

	<small class="text-muted fw-light">
		{format(startDate, "MMMM yyyy")}
		&mdash;
		{#if end}
			{format(endDate, "MMMM yyyy")}
		{:else}
			Present
		{/if}
		{#if end}
			<strong>({nbYears})</strong>
		{/if}
	</small>

	<p class="fw-bold mb-1"><slot name="title" /></p>
	<p class="col-xl-9"><slot name="summary" /></p>
</ListGroupItem>

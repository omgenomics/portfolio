<script>
import { ListGroupItem } from "sveltestrap";

export let start = "January 1 1970";
export let end = null;
export let company = null;
export let url = "#";
export let image = null;

const MONTHS = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];

$: startDate = new Date(start);
$: endDate = end ? new Date(end) : new Date();
$: diff = new Date(endDate - startDate);
$: nbYears = Math.round(diff.getUTCMonth() / 12 + diff.getFullYear() - 1970);
$: txtYears = nbYears === 1 ? "year" : "years";
$: urlTarget = url === "#" ? "" : ` target="_blank"`;
</script>

<ListGroupItem class="p-0 mt-2">
	<h5 class="mt-1 mb-1">
		{#if image}
			<img class="me-1" width="35" height="35" src={image} alt="Logo for {company}" />
		{/if}
		<a class="text-decoration-none" href={url} {urlTarget}> {company} </a>
	</h5>

	<small class="text-muted fw-light">
		{MONTHS[startDate.getUTCMonth()]}
		{startDate.getFullYear()}
		&mdash;
		{#if end}
			{MONTHS[endDate.getUTCMonth()]} {endDate.getFullYear()}
		{:else}
			Present
		{/if}
		{#if end}
			<strong>({nbYears} {txtYears})</strong>
		{/if}
	</small>

	<p class="fw-bold mb-1"><slot name="title" /></p>
	<p class="col-xl-9"><slot name="summary" /></p>
</ListGroupItem>

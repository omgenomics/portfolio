<script>
import { page } from "$app/state";
import { Collapse, Container, Nav, NavItem, NavLink, Navbar, NavbarBrand, Styles } from "@sveltestrap/sveltestrap";
import SocialMedia from "$components/SocialMedia.svelte";
import { MY_NAME, NAVBAR_CATEGORIES, SOCIAL_MEDIA } from "$lib/config";

let { children } = $props();

// Update page title when navigate to a new page
let title = $state("");
$effect(() => {
	const nav = page.url.pathname.split("/")[1];
	if (!nav) {
		title = "";
	} else {
		title = nav[0].toUpperCase() + nav.slice(1) + " - ";
	}
});
</script>

<Styles />

<svelte:head>
	<title>
		{title}
		{MY_NAME}
	</title>
</svelte:head>

<Navbar container expand="md">
	<div class="navbar-brand">
		<NavbarBrand>{MY_NAME}</NavbarBrand>
	</div>
	<Collapse navbar expand="md" isOpen>
		<Nav class="ms-auto">
			<div class="nav">
				{#each NAVBAR_CATEGORIES as category, i}
					{@const label = category[0].toUpperCase() + category.slice(1)}
					{@const url = i === 0 ? "/" : `/${category}`}
					{@const path = page.url.pathname}
					{@const disabled = i === 0 ? path === "/" : path === url || path === `${url}/`}
					<div class="nav-item">
						<NavItem><NavLink href={url} {disabled}>{label}</NavLink></NavItem>
					</div>
				{/each}
			</div>
		</Nav>
	</Collapse>
</Navbar>

<Container md class="mb-5">
	<div class="border-top border-4 mb-3"></div>
	{@render children?.()}

	<footer class="py-3 my-4 border-top ps-0 opacity-75">
		<div class="float-start">
			<div class="small text-end attribution">
				<small>
					<!-- You don't have to keep this notice but we would appreciate it if you did :) -->
					Template by
					<a class="text-reset" href="https://github.com/omgenomics/portfolio" target="_blank">OMGenomics</a>
				</small>
			</div>
		</div>
		<div class="float-end">
			{#each SOCIAL_MEDIA as social}
				<SocialMedia platform={social.platform} href={social.url} />
			{/each}
		</div>
	</footer>
</Container>

<style>
@media only screen and (max-width: 600px) {
	.nav-item {
		width: 100px;
		text-align: center;
	}
	.nav {
		justify-content: center;
	}
	.navbar-brand {
		width: 100%;
		text-align: center;
		margin-bottom: 5px;
		margin-left: 30px; /* Center my name */
	}
}

.attribution {
	color: #999;
}
</style>

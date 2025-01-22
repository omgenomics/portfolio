<script>
import { page } from "$app/stores";
import { MY_NAME, NAVBAR_CATEGORIES } from "$lib/config";
import { Collapse, Container, Nav, NavItem, NavLink, Navbar, NavbarBrand, Styles } from "@sveltestrap/sveltestrap";
import SocialMedia from "$components/SocialMedia.svelte";

let title = "";
let nav = "";
$: path = $page.url.pathname;
$: nav = path.split("/")[1];
$: if (!nav) {
	title = "";
} else {
	title = nav[0].toUpperCase() + nav.slice(1) + " - ";
}
</script>

<Styles />

<svelte:head>
	<title>
		{title} {MY_NAME}
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
					{@const disabled = i === 0 ? path === "/" : path === url || path === `${url}/`}
					<div class="nav-item">
						<NavItem><NavLink href={url} {disabled}>{label}</NavLink></NavItem>
					</div>
				{/each}
			</div>
		</Nav>
	</Collapse>
</Navbar>

<Container md>
	<div class="border-top border-4 mb-3"></div>
	<slot />

	<footer class="py-3 my-4 border-top ps-0 opacity-75">
		<Nav class="float-end">
			<SocialMedia platform="email" href="mailto:myemail" />
			<SocialMedia platform="github" href="https://github.com/my_name" />
			<SocialMedia platform="linkedin" href="https://linkedin.com/in/my_name" />
			<SocialMedia platform="medium" href="https://my_name.medium.com/" />
			<SocialMedia platform="bsky" href="https://bsky.app/profile/my_name" />
		</Nav>
	</footer>
</Container>

<br />

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
</style>

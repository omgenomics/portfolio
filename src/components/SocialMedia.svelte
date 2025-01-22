<script>
import { Icon, NavItem, NavLink, Tooltip } from "sveltestrap";
const ICONS = { email: "envelope-open" };
const NAMES = {
	email: "E-mail",
	github: "GitHub",
	linkedin: "LinkedIn",
	medium: "Medium",
	twitter: "Twitter",
	bsky: "Blue Sky"
};

export let platform = "";
export let href = "#";
</script>

<NavItem>
	<NavLink {href} id="social-{platform}" class="px-2" target={platform === "email" ? "" : `target="_blank"`}>
		<!-- Tooltip -->
		<Tooltip target="social-{platform}">
			{NAMES[platform]}
		</Tooltip>

		{#if platform === "bsky"}
			<img height="14" alt="Bluesky" class="align-baseline" src="https://upload.wikimedia.org/wikipedia/commons/7/7a/Bluesky_Logo.svg" />
		{:else}
			{@const iconName = platform === "email" ? "envelope-open" : platform}
			<Icon name={iconName} />
		{/if}
	</NavLink>
</NavItem>

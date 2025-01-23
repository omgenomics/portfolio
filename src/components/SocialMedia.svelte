<script>
import { Icon, NavItem, NavLink, Tooltip } from "@sveltestrap/sveltestrap";
const NAMES = {
	email: "E-mail",
	github: "GitHub",
	linkedin: "LinkedIn",
	medium: "Medium",
	twitter: "Twitter",
	bsky: "Bluesky"
};

let { platform = "", href = "#" } = $props();
</script>

<NavItem>
	<NavLink {href} id="social-{platform}" class="px-2" target={platform === "email" ? "" : `target="_blank"`}>
		<!-- Tooltip -->
		<Tooltip target="social-{platform}">
			{NAMES[platform]}
		</Tooltip>

		{#if platform === "bsky"}
			<img height="14" width="14" alt="Bluesky" class="align-baseline" src="/assets/bluesky.svg" />
		{:else}
			{@const iconName = platform === "email" ? "envelope-open" : platform}
			<Icon name={iconName} />
		{/if}
	</NavLink>
</NavItem>

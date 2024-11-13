<script lang="ts">
	import { t } from '$lib/i18n';

	import MdEmail from 'svelte-icons/md/MdEmail.svelte';
	import GoMarkGithub from 'svelte-icons/go/GoMarkGithub.svelte';
	import FaLinkedin from 'svelte-icons/fa/FaLinkedin.svelte';
	import FaReddit from 'svelte-icons/fa/FaReddit.svelte';
	import OsmIcon from '$lib/components/icons/OsmIcon.svelte';
	import DiscordIcon from '$lib/components/icons/DiscordIcon.svelte';
	import MastodonIcon from '$lib/components/icons/MastodonIcon.svelte';
	import FaYoutube from 'svelte-icons/fa/FaYoutube.svelte';
	import MatrixIcon from '$lib/components/icons/MatrixIcon.svelte';
</script>

<svelte:head>
	<title>{$t('common.title')} - {$t('contact.title')}</title>
	<meta name="description" content={$t('contact.meta')} />
</svelte:head>

<h1>{$t('contact.title')}</h1>

<p>{$t('contact.description')}</p>

<ul>
	<li class="email">
		<MdEmail title="email" />
		<span><a href="mailto:r@rlin.eu">r@rlin.eu</a></span>
	</li>
	<li class="github">
		<GoMarkGithub title="Github" />
		<span><a href="https://www.github.com/RobinLinde">RobinLinde</a></span>
	</li>
	<li class="linkedin">
		<FaLinkedin title="LinkedIn" />
		<span><a href="https://www.linkedin.com/in/rlineu/">Robin van der Linde</a></span>
	</li>
	<li class="mastodon">
		<MastodonIcon />
		<span><a rel="me" href="https://en.osm.town/@RLin">@RLin@en.osm.town</a></span>
	</li>
	<li class="matrix">
		<MatrixIcon />
		<span><a href="https://matrix.to/#/@robin:rlin.eu">@robin:rlin.eu</a></span>
	</li>
	<li class="osm">
		<OsmIcon />
		<span
			><a href="https://www.openstreetmap.org/user/Robin van der Linde">Robin van der Linde</a
			></span
		>
	</li>
</ul>

<br />

<ul>
	<li class="reddit">
		<FaReddit title="Reddit" /><span
			><a href="https://www.reddit.com/u/RobinVanDerLinde">u/RobinVanDerLinde</a></span
		>
	</li>
	<li class="discord">
		<DiscordIcon />
		<span><a href="https://discord.com/users/177870272047611904">RobinLin#8649</a></span>
	</li>
	<li class="youtube">
		<FaYoutube title="Youtube" />
		<span
			><a href="https://www.youtube.com/channel/UC1Q70h1Tu1xMkQsFGfMzPLQ">Robin van der Linde</a
			></span
		>
	</li>
</ul>

<br />

<p>{$t('contact.linkstack')} <a href="https://me.rlin.eu">me.rlin.eu</a></p>

<style lang="scss">
	p {
		@apply pb-4;
	}

	ul {
		li {
			@apply h-8 flex flex-row gap-2 items-center mb-2 transition-[color] duration-200 w-auto;
			:global(svg) {
				@apply h-8 w-8 p-1 fill-current;
			}
			span {
				@apply h-auto whitespace-nowrap;
			}
			// Custom hover effects
			&.email {
				@apply hover:text-red-600 gdark:hover:text-red-500;
			}
			// Define brands with custom styles
			$brands: discord, osm, mastodon, linkedin, reddit, youtube;
			@each $brand in $brands {
				&.#{$brand} {
					@apply #{'hover:text-' + $brand + '-brand'};
				}
			}
		}
	}
</style>

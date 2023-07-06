<script lang="ts">
	import Tooltip from '$lib/Tooltip.svelte';

	export let src: string;
	export let alt: string;
	export let description: string;
	export let white: boolean = false;
	export let stars: number;
</script>

<div class="skill">
	<img class="logo {white ? 'white' : ''}" {src} {alt} />
	<Tooltip>
		<div slot="content">{description}</div>
		<p class="stars">
			{#each Array(stars) as _, i}
				★
			{/each}
		</p>
	</Tooltip>
</div>

<style>
	.logo {
		object-fit: contain;
		width: 50%;
		height: 5rem;
		margin: auto;
	}
	.white {
		background-color: var(--light);
		padding: 0.5rem 1rem;
		border-radius: 1rem;
	}
	.stars {
		color: var(--main-color);
		margin: 0 auto;
	}
	.skill {
		display: flex;
		flex-direction: column;
	}
</style>

<script lang="ts">
	export let src: string;
	export let alt: string;
	export let white: boolean = false;
	export let stars: number;
</script>

<div class="skill">
	<img class="logo {white ? 'white' : ''}" {src} {alt} />
	<p class="stars">
		{#each Array(stars) as _, i}
			★
		{/each}
	</p>
</div>

<style>
	.logo {
		object-fit: contain;
		width: 50%;
		height: 5rem;
		margin: auto;
		border-radius: 1rem;
	}
	.white {
		background-color: var(--light);
		padding: 0.5rem 1rem;
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

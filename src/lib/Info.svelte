<script lang="ts">
	import { fly } from 'svelte/transition';
	let showInfo = false;
	export let phoneInfoText: string;
	export let desktopInfoText: string;
</script>

<div class="container">
	<input class="info-icon" type="button" value="&#9432;" on:click={() => (showInfo = !showInfo)} />
	{#if showInfo}
		<div class="info-text" transition:fly={{ y: -10, duration: 500 }}>
			<p>
				&#128241;: {phoneInfoText} <br />
				&#128421;: {desktopInfoText}
			</p>
		</div>
	{/if}
</div>

<style>
	.container {
		margin-bottom: 2rem;
		display: flex;
		flex-direction: column;
		border-radius: 2rem;
	}
	.info-icon {
		color: var(--main-color);
		background-color: var(--dark);
		border: none;
		font-size: 2rem;
		margin: auto;
	}
	.info-icon:hover {
		cursor: pointer;
	}
	.info-text {
		border-radius: 2rem;
		background-color: var(--main-color);
		padding: 1rem;
		margin: auto;
	}
</style>

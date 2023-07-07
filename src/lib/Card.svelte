<script lang="ts">
	import { fly } from 'svelte/transition';
	let isHovered = false;

	export let title: string;
	export let src: string;
	export let firstName: string;
	export let secondName: string;
	export let highlightWord: number = 2;
	export let info: object;
</script>

<div class="container">
	<div class="label">
		<h4 class="small-heading">{title}</h4>
	</div>

	<div
		class="card"
		on:mouseenter={() => {
			isHovered = true;
		}}
		on:mouseleave={() => {
			isHovered = false;
		}}
	>
		<img class="background" {src} alt="test" />
		{#key isHovered}
			<div
				transition:fly={{ y: 200, duration: 1500 }}
				class={isHovered ? 'content-increased' : 'content-small'}
			>
				{#if highlightWord == 2}
					<h3 class="heading-small">
						{firstName} <span style="color:var(--main-color)">{secondName}</span>
					</h3>
				{:else}
					<h3 class="heading-small">
						<span style="color:var(--main-color)">{firstName}</span>
						{secondName}
					</h3>
				{/if}

				{#if isHovered}
					<div class="general">
						{#each Object.entries(info) as [category, value]}
							{#if category == 'Website'}
								<div>
									<span style="color:var(--main-color)">{category}:</span>
									<a href={value}>{value}</a>
								</div>
							{:else}
								<div><span style="color:var(--main-color)">{category}:</span> {value}</div>
							{/if}
						{/each}
					</div>
				{/if}
			</div>
		{/key}
	</div>
</div>

<style>
	@media (orientation: landscape) and (min-width: 1001px) {
		.card {
			height: 50vh;
		}
	}
	@media (orientation: portrait) and (max-width: 499px) {
		.card {
			height: 50vh;
		}
	}
	@media (min-width: 500px) and (max-width: 1000px) {
		.card {
			height: 40vh;
		}
	}
	.card {
		position: relative;
		overflow: hidden;
	}
	.container {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.background {
		object-fit: cover;
		height: 100%;
		width: 100%;
		border-radius: 2rem;
	}
	.content-small {
		position: absolute;
		bottom: 0;
		width: 100%;

		border-radius: 0 0 2rem 2rem;
		background: linear-gradient(
			180deg,
			hsla(0, 0%, 0%, 0) 0%,
			hsla(0, 0%, 0%, 0.3) 10%,
			hsl(0, 0%, 0%) 100%
		);
	}
	.content-increased {
		position: absolute;
		bottom: 0;
		width: 100%;
		height: 100%;

		display: grid;
		grid-template-rows: 1fr 50% 1fr;
		border-radius: 2rem;
		background: linear-gradient(
			180deg,
			hsla(0, 0%, 0%, 0) 0%,
			hsla(0, 0%, 0%, 0.4) 10%,
			hsl(0, 0%, 0%) 100%
		);
	}
	.heading-small {
		margin: 2rem;
	}
	.content-increased h3 {
		margin: 2rem;
		text-decoration: underline var(--main-color) 0.2rem;
	}
	.general {
		margin: auto 2rem;
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}
	.label {
		margin: auto;
		display: flex;
		flex-direction: column;
	}

	.label h4 {
		margin: auto;
	}

	a {
		color: inherit;
	}
</style>

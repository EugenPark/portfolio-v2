<script lang="ts">
	import { fly } from 'svelte/transition';

	let images = ['lithuania-u21.jpeg', 'portrait.jpeg', 'vacation-picture.jpg'];
	let leftImage = images[0];
	let rightImage = images[2];
	let middleImage = images[1];

	let animationDistance = 200;
	let leftAnimation: number;
	let middleAnimation: number;
	let rightAnimation: number;

	function shift(direction: number) {
		middleAnimation = animationDistance * direction * -1;
		if (direction === 1) {
			leftAnimation = animationDistance * direction;
			rightAnimation = animationDistance * direction;
			// Right shift
			const lastItem = images.pop();
			images.unshift(lastItem!);
			leftImage = images[0];
			rightImage = images[2];
			middleImage = images[1];
		} else if (direction === -1) {
			leftAnimation = animationDistance * direction;
			rightAnimation = animationDistance * direction;
			// Left shift
			const firstItem = images.shift();
			images.push(firstItem!);
			leftImage = images[0];
			rightImage = images[2];
			middleImage = images[1];
		}
	}
</script>

<div class="carousel">
	<input on:click={() => shift(-1)} type="button" class="arrow" alt="" value="&#60;" />
	<div class="carousel-item left-side">
		{#key leftImage}
			<input
				in:fly={{ x: leftAnimation, duration: 1000 }}
				on:click={() => shift(1)}
				type="image"
				class="portrait"
				src={leftImage}
				alt=""
			/>
		{/key}
	</div>
	<div class="carousel-item middle">
		{#key middleImage}
			<input
				in:fly={{ x: middleAnimation, duration: 1000 }}
				type="image"
				class="portrait"
				src={middleImage}
				alt=""
			/>
		{/key}
	</div>
	<div class="carousel-item right-side">
		{#key middleImage}
			<input
				in:fly={{ x: rightAnimation, duration: 1000 }}
				on:click={() => shift(-1)}
				type="image"
				class="portrait"
				src={rightImage}
				alt=""
			/>
		{/key}
	</div>
	<input on:click={() => shift(1)} type="button" class="arrow" alt="" value="&#62;" />
</div>

<style>
	@media (orientation: landscape) and (min-width: 1001px) {
		.carousel {
			height: 100%;
			max-height: 25vw;
		}
		.arrow {
			display: none;
		}
	}
	@media (orientation: portrait) and (max-width: 499px) {
		.carousel {
			height: 40vh;
		}
		.left-side {
			display: none;
		}
		.right-side {
			display: none;
		}
	}
	@media (min-width: 500px) and (max-width: 1000px) {
		.carousel {
			height: 100%;
		}
		.arrow {
			display: none;
		}
	}
	.right-side {
		transform: translateX(-30%) scale(0.8);
		opacity: 0.6;
		z-index: 0;
	}
	.left-side {
		transform: translateX(30%) scale(0.8);
		opacity: 0.6;
		z-index: 0;
	}
	.middle {
		z-index: 1;
	}
	.portrait {
		width: 100%;
		height: 100%;
		object-fit: cover;
		border-radius: 2rem;
	}
	.carousel {
		display: flex;
		width: 100%;
		margin: auto;
	}
	.carousel-item {
		width: 100%;
		height: 100%;
		margin: auto;
		justify-content: center;
		align-items: center;
	}
	.carousel-item:hover {
		cursor: pointer;
	}
	.arrow {
		font-size: 2rem;
		margin: 0.5rem;
		background-color: #1e1e1e;
		border: 1px solid #1e1e1e;
		color: #f6f6f6;
	}
</style>

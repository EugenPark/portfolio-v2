<script lang="ts">
	import TypeWriter from '$lib/introduction/TypeWriter.svelte';
	import Saos from 'saos';
</script>

<Saos
	animation={'fade-in 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	animation_out={'fade-out 0.5s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	top={250}
	bottom={250}
>
	<div class="container">
		<div class="content">
			<TypeWriter />
			<div class="text">
				<p>
					Welcome to my Portfolio Page. My name is <span style="color: var(--main-color);"
						>Eugene Park</span
					>, and I am a <span style="color: var(--main-color);">Cloud / DevOps</span> Engineer and
					Student. Here you will find a collection of my best
					<span style="color: var(--main-color);">works</span>, showcasing my
					<span style="color: var(--main-color);">skills</span>
					and <span style="color: var(--main-color);">experiences</span>. It's up to you to skip to
					specific sections or to enjoy the journey from the start. If you have any questions or
					remarks please contact me.
					<span style="color: var(--main-color);"
						>Thank you for visiting, I hope you'll enjoy the stay!</span
					>
				</p>
			</div>

			<span class="arrow">&#8595;</span>
		</div>
	</div>
</Saos>

<style>
	@media (orientation: landscape) {
		.content {
			width: 40%;
		}
	}
	@media (orientation: portrait) {
		.content {
			width: 90%;
		}
	}
	.container {
		display: flex;
	}
	.content {
		min-height: 50vh;
		margin: auto;
		justify-content: center;
		display: flex;
		flex-direction: column;
	}
	.text {
		display: flex;
	}
	.text p {
		margin: auto;
		text-align: justify;
		word-wrap: break-word;
	}
	.arrow {
		color: var(--main-color);
		margin-top: 2rem;
		font-size: 3rem;
		text-align: center;
		animation: jumpAnimation 1s infinite;
	}

	@keyframes jumpAnimation {
		0% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(0.5rem);
		}
		100% {
			transform: translateY(0);
		}
	}
</style>

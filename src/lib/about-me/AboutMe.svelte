<script lang="ts">
	import Info from '$lib/Info.svelte';
	import Carousel from './Carousel.svelte';
	import Saos from 'saos';
</script>

<Saos
	animation={'fade-in 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	animation_out={'fade-out 0.5s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	top={250}
	bottom={250}
>
	<div id="about-me" class="container">
		<div class="wrapper">
			<h2 class="heading">About Me</h2>
			<Info
				phoneInfoText="Click on the arrows to change the Pictures"
				desktopInfoText="Click on the pictures to bring them to the front"
			/>
			<div class="content">
				<div class="carousel-wrapper">
					<Carousel />
				</div>
				<div class="text">
					<div>
						<p>
							I was born on <span style="color: var(--main-color);">February 20th, 2001</span>, in
							<span style="color: var(--main-color);">Lulea, Sweden</span>, but my parents moved to
							<span style="color: var(--main-color);">Germany</span>
							shortly after. Therefore I grew up in Aachen and Cologne. My multicultural background,
							with a <span style="color: var(--main-color);">Lithuanian</span> mother and
							<span style="color: var(--main-color);">Korean</span>
							father, provided me not only with insights into different cultures but also provided the
							unique opportunity to learn and speak four languages:
							<span style="color: var(--main-color);">German, English, Lithuanian, and Korean</span
							>.
						</p>
						<p>
							I have always been passionate about sports, and my childhood was filled with many
							opportunities to be active. I was a middle-distance runner in school, and also had the
							honor to play for the youth national
							<span style="color: var(--main-color);">football</span>
							team in Lithuania. Later on, during my Bachelor's degree, I discovered my love for
							<span style="color: var(--main-color);">programming</span>. I especially enjoy the
							problem-solving aspect of it and the challenge of writing complex yet clean software.
							Aside from my professional pursuits, I also enjoy listening to
							<span style="color: var(--main-color);">music</span> and playing the piano in my free
							time and I also love to <span style="color: var(--main-color);">travel</span> and experience
							different cultures from around the world.
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</Saos>

<style>
	@media (orientation: landscape) {
		.content {
			grid-template-columns: 50% 50%;
		}
	}
	@media (orientation: portrait) {
	}
	.container {
		display: flex;
	}
	.wrapper {
		margin: auto;
		display: flex;
		flex-direction: column;
	}
	.content {
		display: grid;
	}
	.heading {
		margin: auto auto 1rem auto;
		color: var(--main-color);
	}
	.carousel-wrapper {
		display: flex;
	}
	.text {
		display: flex;
	}
	.text div {
		margin: auto;
		padding: 1rem;
	}
	.text div p {
		word-wrap: break-word;
		text-align: justify;
	}
</style>

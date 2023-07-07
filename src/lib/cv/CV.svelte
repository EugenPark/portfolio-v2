<script>
	import Info from '$lib/Info.svelte';
</script>

<div class="container">
	<h2 class="heading">CV</h2>
	<Info
		phoneInfoText="Click on the logo to download the cv"
		desktopInfoText="Click on the logo to download the cv"
	/>
	<div class="content">
		<div class="logo-wrapper">
			<a href="/cv.pdf" download>
				<img class="logo" src="/cv.png" alt="CV Cover" />
				<p>CV</p>
			</a>
		</div>
	</div>
</div>

<style>
	.container {
		margin: 3rem 0;
		display: flex;
		flex-direction: column;
	}
	.heading {
		margin: auto;
		color: var(--main-color);
	}
	.content {
		margin: 1rem;
		display: flex;
	}
	.logo {
		object-fit: contain;
		height: 6rem;
		width: 6rem;
		margin: auto;
		border-radius: 1rem;
		padding: 1rem;
	}
	.logo:hover {
		cursor: pointer;
		background-color: var(--main-color);
	}
	.logo-wrapper {
		display: flex;
		flex-direction: column;
		margin: auto;
		text-align: center;
	}
	.logo-wrapper a {
		color: inherit;
	}
</style>

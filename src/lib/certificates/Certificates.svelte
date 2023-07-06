<script>
	import Info from '$lib/Info.svelte';
</script>

<div class="container">
	<h2 class="heading">Certificates</h2>
	<Info
		phoneInfoText="Click on the logos to download the certificates"
		desktopInfoText="Click on the logos to download the certificates"
	/>
	<div class="content">
		<img
			class="logo"
			style="background-color: var(--light); padding: 0.5rem;"
			src="/toefl.png"
			alt="toefl logo"
		/>
		<img class="logo" src="/terraform.webp" alt="terraform logo" />
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
	}
</style>

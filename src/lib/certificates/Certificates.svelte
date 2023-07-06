<script>
	import Info from '$lib/Info.svelte';
</script>

<div class="container">
	<h2 class="heading">Certificates</h2>
	<Info
		phoneInfoText="Click on the logo to download the certificate"
		desktopInfoText="Click on the logo to download the certificate"
	/>
	<div class="content">
		<div class="logo-wrapper">
			<img class="logo" src="/toefl.png" alt="toefl logo" />
			<p>Toefl</p>
		</div>

		<div class="logo-wrapper">
			<img class="logo" src="/terraform.webp" alt="terraform logo" />
			<p>Terraform</p>
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
		margin: auto;
		gap: 1rem;
		display: flex;
	}
	.logo {
		object-fit: contain;
		height: 6rem;
		width: 6rem;
		border-radius: 1rem;
		background-color: var(--light);
		padding: 1rem;
	}
	.logo:hover {
		cursor: pointer;
		background-color: var(--main-color);
	}
	.logo-wrapper {
		display: flex;
		flex-direction: column;
		text-align: center;
	}
</style>

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
			<a href="/toefl-ibt.pdf" download="">
				<img class="logo" src="/toefl.png" alt="toefl logo" />
				<p>Toefl</p>
			</a>
		</div>

		<div class="logo-wrapper">
			<a href="https://www.credly.com/badges/b5d3928a-5c8b-42c3-aa26-3e16b60a4a8d/public_url">
				<img class="logo" src="/terraform.webp" alt="Terraform logo" />
				<p>Terraform</p>
			</a>
		</div>
		<div class="logo-wrapper">
			<a href="/shiftspace-project-certificate.pdf" download>
				<img class="logo" src="/shiftspace-logo.svg" alt="PDF icon" />
				<p>Project Certificate</p>
			</a>
		</div>
	</div>
</div>

<style>
	@media (orientation: landscape) {
		.content {
			flex-direction: row;
		}
	}
	@media (orientation: portrait) {
		.content {
			flex-direction: column;
		}
	}
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
	.logo-wrapper a {
		color: inherit;
	}
</style>

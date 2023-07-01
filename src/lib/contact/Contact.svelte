<div id="contact" class="container">
	<h2 class="heading">Contact</h2>
	<div class="content">
		<div class="logo-wrapper">
			<a href="mailto:eugenepark2001@gmail.com"
				><img class="logo" src="/gmail.png" alt="gmail logo" /></a
			>
			<a href="https://www.linkedin.com/in/eugene-park-3465941b5/"
				><img class="logo" src="/linkedin.svg" alt="linkedin logo" /></a
			>
			<a href="https://github.com/EugenPark"
				><img class="logo" src="/github.png" alt="github logo" /></a
			>
		</div>
	</div>
</div>

<style>
	.container {
		display: flex;
		gap: 2rem;
		flex-direction: column;
		margin: 3rem 0;
	}
	.content {
		background-color: var(--main-color);
		padding: 2rem;
		border-radius: 1rem;
		display: flex;
	}
	.heading {
		margin: auto;
		color: var(--main-color);
	}

	.logo-wrapper {
		display: flex;
		margin: auto;
		gap: 2rem;
	}
	.logo {
		height: 3rem;
		width: 3rem;
		object-fit: contain;
		margin: auto;
	}
</style>

<script lang="ts">
	let lightBackground = false;
</script>

<div id="contact" class="container">
	<h2 class="heading">Contact</h2>
	<div class="content">
		<div class="logos">
			<a href="mailto:eugenepark2001@gmail.com">
				<div class="logo-wrapper">
					<img class="logo" src="/gmail.png" alt="gmail logo" />
					<p class="label">Email</p>
				</div>
			</a>
			<a href="https://www.linkedin.com/in/eugene-park-3465941b5/">
				<div class="logo-wrapper">
					<img class="logo" src="/linkedin.svg" alt="linkedin logo" />
					<p class="label">LinkedIn</p>
				</div>
			</a>
			<a
				href="https://github.com/EugenPark"
				on:mouseenter={() => (lightBackground = true)}
				on:mouseleave={() => (lightBackground = false)}
			>
				<div class="logo-wrapper">
					<img
						class="logo"
						src="/github.png"
						alt="github logo"
						style={lightBackground ? 'background-color: var(--light);' : ''}
					/>
					<p class="label">GitHub</p>
				</div>
			</a>
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

	.logos {
		display: flex;
		margin: auto;
		gap: 2rem;
	}
	.logos a {
		padding: 0.5rem;
		border-radius: 1rem;
		display: flex;
		flex-direction: column;
		color: var(--dark);
	}
	.logos a:hover {
		background-color: var(--dark);
		color: var(--main-color);
	}

	.logo-wrapper {
		display: flex;
		flex-direction: column;
		margin: auto;
		gap: 0.5rem;
	}

	.logo {
		height: 3rem;
		width: 3rem;
		object-fit: contain;
		margin: auto;
		padding: 0.1rem;
	}

	.label {
		margin: 0 auto;
	}
</style>

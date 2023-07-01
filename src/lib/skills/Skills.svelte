<script lang="ts">
	import Saos from 'saos';
	import Logo from './Logo.svelte';
</script>

<svelte:head><title>EP - Skills</title></svelte:head>
<Saos
	animation={'fade-in 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	animation_out={'fade-out 0.5s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	top={250}
	bottom={250}
>
	<div id="skills" class="container">
		<h2 class="heading">Skills</h2>
		<div class="content">
			<div class="category">
				<h3 class="heading">Programming</h3>
				<Logo stars={4} src="/python-logo.png" alt="Python Logo" />
				<Logo stars={4} src="/java-logo.png" alt="Java Logo" />
				<Logo stars={4} src="/javascript-logo.png" alt="JavaScript Logo" />
				<Logo stars={4} src="/typescript-logo.png" alt="TypeScript Logo" />
				<Logo stars={3} src="/bash-logo.png" alt="Bash Logo" />
				<Logo stars={1} src="/cpp-logo.png" alt="C++ Logo" />
			</div>

			<div class="category">
				<h3 class="heading">Frameworks</h3>
				<Logo stars={4} src="/svelte-logo.png" alt="Svelte Logo" />
				<Logo stars={3} src="/react-logo.png" alt="React Logo" />
				<Logo stars={3} white src="/nextjs-logo.png" alt="NextJS Logo" />
				<Logo stars={2} src="/angular-logo.png" alt="Angular Logo" />
			</div>

			<div class="category">
				<h3 class="heading">Technologies</h3>
				<Logo stars={5} src="/docker-logo.webp" alt="Docker Logo" />
				<Logo stars={5} white src="/argocd-logo.png" alt="ArgoCD Logo" />
				<Logo stars={4} src="/kubernetes-logo.png" alt="Kubernetes Logo" />
				<Logo stars={3} white src="/helm-logo.png" alt="Helm Logo" />
			</div>

			<div class="category">
				<h3 class="heading">Languages</h3>
				<Logo stars={5} white src="/deutschland.png" alt="Deutsche Flagge" />
				<Logo stars={4} src="/britisch.png" alt="Britische Flagge" />
				<Logo stars={4} src="/litauen.jpeg" alt="Litauische Flagge" />
				<Logo stars={2} src="/korea.png" alt="Koreanische Flagge" />
			</div>
		</div>
	</div>
</Saos>

<style>
	@media (orientation: landscape) {
		.content {
			grid-template-columns: 25% 25% 25% 25%;
		}
	}
	@media (orientation: portrait) {
		.content {
			grid-template-columns: 50% 50%;
		}
	}

	.container {
		display: flex;
		flex-direction: column;
		margin: 3rem 0;
		padding: 0 10%;
	}

	.content {
		display: grid;
		gap: 1rem;
	}
	.category {
		display: flex;
		flex-direction: column;
		row-gap: 1rem;
	}

	.heading {
		margin: 0 auto 1rem auto;
		color: var(--main-color);
	}
</style>

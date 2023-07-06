<script lang="ts">
	import Saos from 'saos';
	import Logo from './Logo.svelte';
	import Info from '$lib/Info.svelte';
</script>

<Saos
	animation={'fade-in 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	animation_out={'fade-out 0.5s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}
	top={250}
	bottom={250}
>
	<div id="skills" class="container">
		<h2 class="heading">Skills</h2>
		<Info
			phoneInfoText="Click on the stars for context"
			desktopInfoText="Hover over the stars for context"
		/>
		<div class="content">
			<div class="category">
				<h3 class="heading">Programming</h3>
				<Logo stars={4} src="/python-logo.png" alt="Python Logo" description="Advanced" />
				<Logo stars={4} src="/java-logo.png" alt="Java Logo" description="Advanced" />
				<Logo stars={4} src="/javascript-logo.png" alt="JavaScript Logo" description="Advanced" />
				<Logo stars={4} src="/typescript-logo.png" alt="TypeScript Logo" description="Advanced" />
				<Logo stars={3} src="/bash-logo.png" alt="Bash Logo" description="Intermediate" />
				<Logo stars={1} src="/cpp-logo.png" alt="C++ Logo" description="Novice" />
			</div>

			<div class="category">
				<h3 class="heading">Frameworks</h3>
				<Logo stars={4} src="/svelte-logo.png" alt="Svelte Logo" description="Advanced" />
				<Logo stars={3} src="/react-logo.png" alt="React Logo" description="Intermediate" />
				<Logo stars={3} white src="/nextjs-logo.png" alt="NextJS Logo" description="Intermediate" />
				<Logo stars={2} src="/angular-logo.png" alt="Angular Logo" description="Beginner" />
			</div>

			<div class="category">
				<h3 class="heading">Technologies</h3>
				<Logo stars={5} src="/docker-logo.webp" alt="Docker Logo" description="Expert" />
				<Logo stars={5} white src="/argocd-logo.png" alt="ArgoCD Logo" description="Expert" />
				<Logo stars={4} src="/kubernetes-logo.png" alt="Kubernetes Logo" description="Advanced" />
				<Logo stars={3} white src="/helm-logo.png" alt="Helm Logo" description="Intermediate" />
			</div>

			<div class="category">
				<h3 class="heading">Languages</h3>
				<Logo
					stars={5}
					white
					src="/deutschland.png"
					alt="Deutsche Flagge"
					description="Native Language"
				/>
				<Logo stars={5} src="/litauen.jpeg" alt="Litauische Flagge" description="Native Language" />
				<Logo stars={4} src="/britisch.png" alt="Britische Flagge" description="Business Fluent" />
				<Logo stars={2} src="/korea.png" alt="Koreanische Flagge" description="Good Knowledge" />
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
	}

	.content {
		display: grid;
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

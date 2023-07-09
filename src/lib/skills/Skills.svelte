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
				<Logo stars={4} src="/logos/python.png" alt="Python Logo" description="Advanced" />
				<Logo stars={4} src="/logos/java.png" alt="Java Logo" description="Advanced" />
				<Logo stars={4} src="/logos/javascript.png" alt="JavaScript Logo" description="Advanced" />
				<Logo stars={4} src="/logos/typescript.png" alt="TypeScript Logo" description="Advanced" />
				<Logo stars={3} src="/logos/bash.png" alt="Bash Logo" description="Intermediate" />
				<Logo stars={1} src="/logos/cpp.png" alt="C++ Logo" description="Novice" />
			</div>

			<div class="category">
				<h3 class="heading">Frameworks</h3>
				<Logo stars={4} src="/logos/svelte.png" alt="Svelte Logo" description="Advanced" />
				<Logo stars={3} src="/logos/react.png" alt="React Logo" description="Intermediate" />
				<Logo
					stars={3}
					white
					src="/logos/nextjs.png"
					alt="NextJS Logo"
					description="Intermediate"
				/>
				<Logo stars={2} src="/logos/angular.png" alt="Angular Logo" description="Beginner" />
			</div>

			<div class="category">
				<h3 class="heading">Technologies</h3>
				<Logo stars={5} src="/logos/docker.webp" alt="Docker Logo" description="Expert" />
				<Logo stars={5} white src="/logos/argocd.png" alt="ArgoCD Logo" description="Expert" />
				<Logo stars={4} src="/logos/kubernetes.png" alt="Kubernetes Logo" description="Advanced" />
				<Logo stars={3} white src="/logos/helm.png" alt="Helm Logo" description="Intermediate" />
			</div>

			<div class="category">
				<h3 class="heading">Languages</h3>
				<Logo
					stars={5}
					white
					src="/logos/germany.png"
					alt="German Flag"
					description="Native Language"
				/>
				<Logo
					stars={5}
					src="/logos/lithuania.png"
					alt="Lithuanian Flag"
					description="Native Language"
				/>
				<Logo
					stars={4}
					src="/logos/united-kingdom.png"
					alt="British Flag"
					description="Business Fluent"
				/>
				<Logo
					stars={2}
					src="/logos/south-korea.png"
					alt="South Korean Flag"
					description="Good Knowledge"
				/>
				<Logo stars={1} src="/logos/france.png" alt="French Flag" description="Basic Knowledge" />
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
		row-gap: 3rem;
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

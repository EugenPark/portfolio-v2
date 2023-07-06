<script lang="ts">
	import Navbar from '$lib/Navbar.svelte';
	import Introduction from '$lib/introduction/Introduction.svelte';
	import AboutMe from '$lib/about-me/AboutMe.svelte';
	import Education from '$lib/education/Education.svelte';
	import Experience from '$lib/experience/Experience.svelte';
	import Skills from '$lib/skills/Skills.svelte';
	import Contact from '$lib/contact/Contact.svelte';
	import Certificates from '$lib/certificates/Certificates.svelte';
	import Cv from '$lib/cv/CV.svelte';
</script>

<div class="wrapper">
	<Introduction />
</div>
<Navbar />
<div class="wrapper">
	<Skills />
	<AboutMe />
	<Education />
	<Experience />
	<Certificates />
	<Cv />
	<Contact />
</div>

<!-- index.svelte -->

<style>
	@media (orientation: landscape) {
		.wrapper {
			padding: 0 10%;
		}
	}
	@media (orientation: portrait) {
	}
	:global(body) {
		background-color: var(--dark);
		color: var(--light);
	}

	:root {
		--main-color: #6ec895;
		--secondary-color: #c86ea1;
		--dark: #1e1e1e;
		--light: #f6f6f6;
	}

	@keyframes -global-fade-in {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes -global-fade-out {
		0% {
			opacity: 1;
		}
		100% {
			opacity: 0;
		}
	}
</style>

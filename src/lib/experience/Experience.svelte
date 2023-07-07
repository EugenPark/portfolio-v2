<script>
	import Card from '$lib/Card.svelte';
	import Info from '$lib/Info.svelte';
	const taod = {
		src: '/taod.webp',
		firstName: 'Taod',
		secondName: 'Consulting',
		info: {
			Title: 'DevOps & Cloud-Platform Engineer',
			Position: 'Working Student / Junior',
			Timespan: 'September 2022 - May 2023',
			Technologies: 'Python, Kubernetes, ArgoCD, Helm, Terraform',
			Website: 'https://www.taod.de/'
		},
		highlightWord: 1,
		title: 'DevOps Engineer'
	};
	const akka = {
		src: '/akka.png',
		firstName: 'Akka',
		secondName: 'Technologies',
		info: {
			Title: 'IoT Engineer',
			Position: 'Working Student',
			Timespan: 'March 2021 - Oktober 2021',
			Technologies: 'C++, Bash, Linux',
			Website: 'https://www.akka-technologies.com/'
		},
		highlightWord: 1,
		title: 'IoT Engineer'
	};
	const megatronik = {
		src: '/megatronik.png',
		firstName: 'Megatronik',
		secondName: '',
		info: {
			Title: 'Software Engineer',
			Position: 'Freelancer',
			Timespan: 'November 2021 - July 2022',
			Technologies: 'PHP, JavaScript, Bootstrap, Python',
			Website: 'https://megatronik.org/'
		},
		highlightWord: 1,
		title: 'Software Engineer'
	};
</script>

<div id="experience" class="container">
	<h2 class="heading">Experience</h2>
	<Info
		phoneInfoText="Click on the cards for more detailed information"
		desktopInfoText="Hover over the cards for more detailed information"
	/>
	<div class="content">
		<Card {...akka} />
		<Card {...megatronik} />
		<Card {...taod} />
		<div />
	</div>
</div>

<style>
	@media (orientation: landscape) {
		.content {
			grid-template-columns: 1fr 1fr 1fr;
		}
	}
	@media (orientation: portrait) {
		.content {
			grid-template-columns: 1fr;
		}
	}
	.container {
		margin: 3rem 0;
		display: flex;
		flex-direction: column;
	}

	.content {
		display: grid;
		gap: 2rem;
	}
	.heading {
		margin: 1rem auto;
		color: var(--main-color);
	}
</style>

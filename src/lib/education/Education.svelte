<script lang="ts">
	import Info from '$lib/Info.svelte';
	import Card from '../Card.svelte';
	const highschool = {
		src: '/norbert_gymnasium_knechtsteden.jpg',
		firstName: 'Norbert-Gymnasium',
		secondName: 'Knechtsteden',
		info: {
			Degree: 'Abitur',
			Timespan: '2011-2019',
			GPA: 1.5,
			'Main Courses': 'Sports, English, Math, Social Sciences'
		},
		title: 'Middle- & Highschool'
	};
	const bachelor = {
		src: '/university_of_cologne.jpg',
		firstName: 'Universität zu',
		secondName: 'Köln',
		info: {
			Degree: 'Bachelor',
			Course: 'Information Systems',
			Timespan: '2019-2023',
			GPA: 1.7,
			Rank: 'Top 15%',
			Thesis: 'Representing Business Processes in Simulations',
			'Thesis Grade': '1.0'
		},
		title: 'University - Bachelor'
	};
	const master = {
		src: '/kth_royal_institute_of_technology.jpeg',
		firstName: 'KTH',
		secondName: 'Royal Institute of Technology',
		info: {
			Degree: 'Master',
			Course: 'Software Engineering of Distributed Systems',
			Timespan: '2023-2025',
			Start: '28th August 2023'
		},
		highlightWord: 1,
		title: 'University - Master'
	};
</script>

<div id="education" class="container">
	<h2 class="heading">Education</h2>
	<Info
		phoneInfoText="Click on the cards for more detailed information"
		desktopInfoText="Hover over the cards for more detailed information"
	/>
	<div class="content">
		<Card {...highschool} />
		<Card {...bachelor} />
		<Card {...master} />
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
		margin: 3rem auto;
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

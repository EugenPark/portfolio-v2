<script lang="ts">
	import { fly } from 'svelte/transition';

	let open = false;
	function toggleMenu() {
		open = !open;
	}
</script>

<div class="container">
	<div class="mobile">
		<div class="upper-menu">
			<div class="logo"><h2>Eugene <span style="color: var(--main-color);">Park</span></h2></div>
			<div class="menu-icon">
				{#if open}
					<input on:click={toggleMenu} type="button" value="&#10006;" />
				{:else}
					<input on:click={toggleMenu} type="button" value="&#9776;" />
				{/if}
			</div>
		</div>

		{#if open}
			<div class="menu" transition:fly={{ y: -50, duration: 500 }}>
				<a href="#skills">Skills</a>
				<a href="#about-me">AboutMe</a>
				<a href="#education">Education</a>
				<a href="#experience">Experience</a>
				<a href="#certificates">Certificates</a>
				<a href="#contact">Contact</a>
			</div>
		{/if}
	</div>

	<div class="desktop">
		<div class="logo"><h2>Eugene <span style="color: var(--main-color);">Park</span></h2></div>
		<div class="menu">
			<a href="#skills">Skills</a>
			<a href="#about-me">About Me</a>
			<a href="#education">Education</a>
			<a href="#experience">Experience</a>
			<a href="#certificates">Certificates</a>
			<a href="#contact">Contact</a>
		</div>
	</div>
</div>

<style>
	@media (orientation: landscape) {
		.desktop {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
		}
		.mobile {
			display: none;
		}
		.menu {
			display: flex;
			gap: 2rem;
			flex-direction: row;
		}
		.menu a {
			margin: auto;
			white-space: nowrap;
		}
	}
	@media (orientation: portrait) {
		.desktop {
			display: none;
		}
		.mobile {
			display: flex;
			flex-direction: column;
		}
		.menu {
			display: flex;
			flex-direction: column;
			gap: 1rem;
		}
	}
	@media only screen and (max-width: 25rem) {
		.logo h2 {
			font-size: 1.4rem;
		}
	}
	.container {
		position: sticky;
		position: -webkit-sticky;
		top: 0;
		padding: 1rem 5%;
		background-color: var(--dark);
		z-index: 1;
	}
	.upper-menu {
		display: flex;
	}
	.menu-icon {
		margin: auto 0 auto auto;
	}
	.menu-icon input {
		background-color: var(--dark);
		color: var(--main-color);
		border: none;
		font-size: 2rem;
	}
	.menu a {
		text-decoration: none;
		color: var(--light);
	}
	.menu a:hover {
		color: var(--main-color);
	}
</style>

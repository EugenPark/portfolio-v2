<script lang="ts">
	let showTooltip = false;
</script>

<div
	class="tooltip"
	on:mouseenter={() => {
		showTooltip = true;
	}}
	on:mouseleave={() => (showTooltip = false)}
>
	<slot />
	{#if showTooltip}
		<span class="tooltiptext"><slot name="content" /></span>
	{/if}
</div>

<style>
	@media (orientation: landscape) {
		.tooltiptext {
			width: 80%;
			left: 10%;
		}
	}
	@media (orientation: portrait) {
		.tooltiptext {
			width: 100%;
			left: 0;
		}
	}
	.tooltip {
		position: relative;
		display: flex;
	}

	.tooltiptext {
		background-color: var(--main-color);
		color: black;
		text-align: center;
		border-radius: 6px;
		position: absolute;
		z-index: 1;
		top: 150%;
		padding: 0.5rem 0;
	}

	.tooltip .tooltiptext::after {
		content: '';
		position: absolute;
		bottom: 100%;
		left: 50%;
		margin-left: -5px;
		border-width: 5px;
		border-style: solid;
		border-color: transparent transparent var(--main-color) transparent;
	}
</style>

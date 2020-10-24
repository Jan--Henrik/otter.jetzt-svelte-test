<script>
	import { fade } from 'svelte/transition';
	let ott = false;
	let src = 'images/otter.jpeg';
</script>

<main>
	{#if !ott}
		<div><button class="button" in:fade={{ delay: 600 }} out:fade on:click={() => ott = !ott}>Otter?</button></div>
	{:else}
		<img {src} in:fade={{ delay: 600 }}  alt="An Otter!">
	{/if}
</main>

<style>
	:global(body) {
		background-color: #86B3C8;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	div {
	display: flex;
	height: 100%;
	align-items: center;
	justify-content: center;
	flex-direction: column;
	color: white;
	text-transform: uppercase;
	font-size: 4em;
	font-weight: 100;
	}

	button {
		padding: 0;
		border: none;
		font: ubuntu;
		color: inherit;
		background-color: #f76027;
		cursor: pointer;
		border-radius: 55px;
		padding: 15px 20px;
	}

	button:focus {
		outline: 0;
	}

	.button:hover {
  	box-shadow: 0 3px 6px black;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
			left: 50%;
			position: absolute;
			top: 50%;
			transform: translate(-50%, -50%);
		}
	}
</style>

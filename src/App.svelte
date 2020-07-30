<script>
	import Pokedex from './components/Pokedex.svelte';
</script>

<main class="App">
	<Pokedex />
</main>

<style>
	:root {
		--red: #dd082f;
		--dark-red: #3b020d;
		--green: #2ff901;
		--yellow: #ffcc02;
		--sky: #01fbfb;
		--orange: #ffcc02;
		--blue: #519afb;
		font-size: 16px;
	}

	:global(body){
		margin: 0;
		background-color: var(--dark-red);
	}

	:global(h1, h2){
		margin: 0;
	}

	:global(ul){
		padding: 0;
		list-style: none;
	}

	.App {
		display: flex;
		align-items: center;
		height: 100%;
		overflow: hidden;
		margin: 0;
		font-family: system-ui;
	}
</style>


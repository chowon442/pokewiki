<script>
	import { arrPokemon } from '../stores/pokestore';
	import PokemonCard from '../components/PokemonCard.svelte';

	let searchTerm = '';
	let filteredPokemon = [];

	// reactivity
	$: {
		if (searchTerm) {
			filteredPokemon = $arrPokemon.filter((pokemon) => pokemon.name.includes(searchTerm));
		} else {
			filteredPokemon = [...$arrPokemon];
		}
	}
</script>

<svlete:head>
	<title>포켓몬 위키</title>
</svlete:head>

<h1 class="my-8 text-4xl font-bold text-center underline">포켓몬 위키 사이트</h1>

<input
	class="w-full p-4 mb-8 text-lg border-2 border-gray-200 rounded-md"
	type="text"
	placeholder="포켓몬 검색"
	bind:value={searchTerm}
/>

<div class="grid grid-cols-2 gap-4 md:grid-cols-3">
	{#each filteredPokemon as pokemon}
		<PokemonCard {pokemon} />
	{/each}
</div>

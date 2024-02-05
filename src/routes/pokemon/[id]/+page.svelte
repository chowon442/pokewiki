<script>
	import { arrPokemon } from '../../../stores/pokestore.js';

	export let data;
	const { pokemon } = data;
</script>

<h1 class="text-4xl text-center text-red-500">포켓몬 상세페이지</h1>

<div class="flex flex-col items-center text-2xl">
	<h1 class="my-8 text-4xl text-center">{pokemon.name}</h1>
	<h1 class="my-8 text-4xl text-center">{$arrPokemon[pokemon.id - 1].name}</h1>

	<p>타입: {pokemon.types[0].type.name}</p>
	<p>키: {pokemon.height}</p>
	<p>무게: {pokemon.weight}</p>
	<img class="w-40 h-40" src={pokemon.sprites['front_default']} alt={pokemon.name} />
</div>

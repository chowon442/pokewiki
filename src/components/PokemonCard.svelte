<script>
	export let pokemon;

	import { fade } from 'svelte/transition';
</script>

<a
	class="flex flex-col items-center p-6 text-center text-gray-800 bg-gray-100 rounded-md shadow-sm hover:shadow-md"
	href={`/pokemon/${pokemon.id}`}
	transition:fade
>
	<img class="w-40 h-40" src={pokemon.image} alt={pokemon.name} />
	<h2 class="text-2xl">{pokemon.id}. {pokemon.name}</h2>
</a>

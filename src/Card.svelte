<script>
  import { getContext } from "svelte";
  import Pokemon from "./Pokemon.svelte";

  export let pokemon;

  const { open } = getContext("simple-modal");

  const showPokemon = () => open(Pokemon, { pokemon });
</script>

<style>
  p {
    color: hotpink;
  }

  article {
    width: 100%;
    height: 100px;
  }

  .container {
    height: 500px;
  }
</style>

<article on:click={showPokemon} class="container">
  <img width="200px" src={pokemon.imageSrc} alt="Pokemon name" />
  <p class="name" data-testid="banana">Name: {pokemon.name}</p>
  <p class="name" data-testid="card-description">Price: {pokemon.price}</p>
</article>

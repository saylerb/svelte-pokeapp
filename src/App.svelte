<script>
  import { onMount } from "svelte";
  import Modal from "svelte-simple-modal";
  import Card from "./Card.svelte";
  import { getPokemons } from "./api.js";
  import _ from "lodash";

  let pokemons = [];

  onMount(async function() {
    pokemons = await getPokemons();
    pokemons = _.orderBy(pokemons, ["price"], ["desc"]);
  });
</script>

<style>
  main {
    padding: 1em;
    font-family: "Comic Sans";
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
</style>

<Modal>
  <main>
    <h1>Pokemon</h1>
    {#each pokemons as pokemon}
      <Card {pokemon} />
    {/each}
  </main>
</Modal>

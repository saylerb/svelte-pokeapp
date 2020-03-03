<script>
  export let pokemon;
</script>

<style>
  article {
    padding: 2em;
    margin-top: 0;
  }
</style>

<article>
  <h1>{pokemon.name}</h1>
  <h2>{pokemon.price}</h2>
  <img src={pokemon.imageSrc} alt="Pokemon" width="201px" />
  <p>{pokemon.description}</p>
</article>

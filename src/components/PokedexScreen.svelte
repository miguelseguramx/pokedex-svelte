<script>
  import Stat from './Stat.svelte'
  export let error
  export let loading
  export let pokemon
</script>

<!-- Lo mejor que podrimos hacer aqui es usar un #await  -->
<!-- Lo mejor que podrimos hacer aqui es usar un :then  -->
<!-- Lo mejor que podrimos hacer aqui es usar un :catch  -->
<!-- Seria hacer trampa o que procede -->
<div class="pokedex-screen">
  {#if error}
    <img
      src='img/error.gif'
      alt="Hubo un error buscando tu pokemon"
      class="pokedex-no-screen"
    />
  {:else if !pokemon || loading}
    <img
      src='img/loading.gif'
      alt="Aun no hay ningun pokeom"
      class="pokedex-no-screen"
    />
  {:else}
    <div class="pokemon-info">
      <h2 class="pokemon-name">{pokemon.name}</h2>
      <img class="pokemon-img" src={pokemon.sprites.front_default} alt={pokemon.name} />
      <ul class="pokemon-stats">
        {#each pokemon.stats as item (item.stat.name)}
          <Stat item={item}/>
        {/each}
      </ul>
    </div>
  {/if}
</div>

<style>
  .pokedex-screen {
    background: white;
    border: 2px solid black;
    border-radius: 10px;
    height: 100%;
    display: flex;
    align-items: center;
  }
  .pokedex-no-screen{
    width: 100%;
    height: 100%;
  }


  .pokemon-info{
    padding: 0.8rem;
    flex-grow: 1;
    display: grid;
    grid-template-columns: 40% calc(60% - 0.8rem);
    grid-template-rows: 35px 1fr;
    grid-column-gap: 0.8rem;
    grid-row-gap: 0.8rem;
    grid-template-areas:
      "title title"
      "img   stats";
  }
  .pokemon-name{
    text-align: center;
    text-transform: capitalize;
    grid-area: title;
    font-weight: 700;
  }
  .pokemon-img{
    width: 100%;
    transform: scale(1.2);
    align-self: center;
    grid-area: img;
  }
  .pokemon-stats{
    grid-area: stats;
    font-size: 0.9rem;
  }
</style>

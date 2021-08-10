<script>
  import GameItem from "./GameItem.svelte";
  export let boardGames = [];
</script>
<div>
  {#each boardGames as game}
	  <GameItem {...game} on:delete-card />
  {/each}
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
    width: 100%;
    align-items: center;
  }

  @media (min-width: 960px) {
    div {
      flex-direction: row;
      gap: 1rem;
      max-width: 80%;
      margin: auto;
    }
  }
</style>
<script>
  import GameCards from "./components/GameCards.svelte";
  import AddGame from "./components/AddGame.svelte";
  import Button from "./ui/Button.svelte";
  let boardGames = [
    {
      id: "default1",
      title: "Root",
      creator: "Leder Games",
      imageUrl:
        "https://cdn.shopify.com/s/files/1/0106/0162/7706/products/1-RootGameBox-Edit-Web_1024x1024.png?v=1595294735",
      description:
        "Root is a game of woodland might and right. Stalk the woods as one of the Vagabonds, seize the initiative with the Eyrie birds of prey, rule over your subjects as the Marquise de Cat, or command the Woodland Alliance to create a new order. With creatures and cunning, you'll rule a fantastic forest kingdom in the ultimate asymmetric board game of adventure and war.",
      url:
        "https://ledergames.com/products/root-a-game-of-woodland-might-and-right",
      rating: 5
    },
    {
      id: "default2",
      title: "Scythe",
      creator: "Stonemaier",
      imageUrl:
        "https://stonemaiergames.com/wp-content/uploads/2018/12/3d-scythe-768x767.png",
      description:
        "Scythe is an engine-building, asymmetric, competitive board game set in an alternate-history 1920s period. It is a time of farming and war, broken hearts and rusted gears, innovation and valor.",
      url: "https://stonemaiergames.com/games/scythe/",
      rating: 5
    }
  ];

  let editReviews = false;

  function editGameList(event) {
    const newGame = event.detail;
    boardGames = [...boardGames, newGame];
    editReviews = false;
  }

  function deleteCard(event) {
    const deletedCardId = event.detail;
    boardGames = boardGames.filter(game => game.id !== deletedCardId);
  }
</script>

<main>
<h1>Board to Death</h1>
  {#if editReviews}
  <AddGame on:save={editGameList} on:close={() => editReviews = false} />
  {:else}
  <div class="close-btn">
    <Button mode="submit" on:click={() => editReviews = true}>Add Review</Button>
  </div>
  {/if}
  <GameCards {boardGames} on:delete-card={deleteCard}/>
</main>


<style>
  h1 {
    text-align: center;
    font-size: 3rem;
    margin: 0.4rem;
  }

  .close-btn {
    text-align: center;
    margin-bottom: 1rem;
  }
</style>
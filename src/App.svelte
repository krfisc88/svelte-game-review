<script>
  import GameCards from "./components/GameCards.svelte";
  import AddGame from "./components/AddGame.svelte";
  const boardGames = [
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
</script>

<main>
  <AddGame />
  <GameCards {boardGames}/>
</main>


<style>
</style>
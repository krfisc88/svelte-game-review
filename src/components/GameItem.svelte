<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  export let id;
  export let title;
  export let creator;
  export let imageUrl = null;
  export let description;
  export let url = null;
  export let rating = "";
  let focused = false;

  const deleteCard = () => {
    dispatch("delete-card", id);
  };
</script>

<article on:mouseover={() => focused = true} on:mouseleave={() => focused = false}>
  {#if focused}
    <button on:click={deleteCard} class="delete">x</button>
  {/if}
  <header>
    <h1><a href={url}>{title}</a></h1>
    <h2>By {creator}</h2>
  </header>
  <div class="body">
    <div class="product-image">
        <a href={url} >
          <img src="{imageUrl}" alt="{title}">
        </a>
    </div>
    <div class="content">
      <p>{description}</p>  
    </div>
  </div>
  <footer>
    {#each Array(rating) as _}
        <span>&#9733;</span>
    {/each}
    
  </footer>
</article>

<style>
  article {
    position: relative;
    margin-bottom: 2rem;
    background-color: white;
    border-radius: 15px;
    padding: 1rem;
    box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.2),
      -2px -2px 12px rgba(255, 255, 255, 0.1);
    width: 100%;
    min-width: 12rem;
  }
  /* Header Styles */
  h1 {
    margin-top: 0;
    margin-bottom: 0;
  }

  h1 a {
    color: black;
    text-decoration: none;
  }

  h1 a:hover {
    color: red;
  }

  h2 {
    margin: 0;
    font-size: 1.2rem;
  }

  /* Image Styles */
  .product-image {
    height: 10rem;
  }

  img {
    height: 100%;
  }

  /* Content Styles */
  .body {
    display: flex;
    gap: 1rem;
    align-items: center;
    flex-direction: column;
  }

  /* Button styles */
  .delete {
    position: absolute;
    right: 1rem;
    top: 1rem;
    background-color: transparent;
    border: 3px solid #ff8811;
    color: #ff8811;
    border-radius: 50%;
    font-size: 1rem;
    font-weight: 600;
  }

  .delete:hover {
    background-color: #ff8811;
    color: white;
  }

  /* Media Queries */
  @media (min-width: 960px) {
    .body {
      flex-direction: row;
      align-items: stretch;
      height: 100%;
    }

    .content p {
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 7;
      overflow: hidden;
    }
  }
</style>
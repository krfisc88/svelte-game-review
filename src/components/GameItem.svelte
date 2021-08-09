<script>
  export let id;
  export let title;
  export let creator;
  export let imageUrl = null;
  export let description;
  export let url = null;
  export let rating = 0;
</script>

<article>
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
<script>
  export let type = "submit";
</script>

<button {type} on:click>
  <slot />
</button>

<style>
  button {
    background-color: #ff8811;
    border: none;
    font-size: 1.2rem;
    padding: 0.5rem;
    border-radius: 0.3rem;
    margin: 1rem;
    color: white;
    font-weight: 600;
  }
</style>
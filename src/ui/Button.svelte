<script>
  export let type = "submit";
  export let mode = "";
</script>

<button class={mode} {type} on:click>
  <slot />
</button>

<style>
  .submit {
    background-color: #ff8811;
    border: none;
    font-size: 1.2rem;
    padding: 0.5rem;
    border-radius: 0.3rem;
    margin: 1rem;
    color: white;
    font-weight: 600;
  }

  .submit:hover {
    background-color: #faac40;
  }

  .cancel {
    position: absolute;
    right: 1rem;
    top: 1rem;
    background-color: transparent;
    border: 3px solid #ff8811;
    color: #ff8811;
    border-radius: 50%;
    font-size: 1rem;
  }

  .cancel::before {
    content: "x";
    font-weight: 600;
  }

  .cancel:hover {
    background-color: #ff8811;
    color: white;
  }
</style>
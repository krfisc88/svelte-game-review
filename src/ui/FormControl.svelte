<script>
    export let id;
    export let value;
    export let type = "text";
    export let controlType = null;
    export let rows = null;
</script>

<div>
    <label for={id}>
        <slot />
    </label>
    {#if controlType === 'textarea'}
        <textarea {id} {rows}  {value} on:input/>
    {:else}
        <input {type} {id} {value} on:input/>
    {/if}
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
  }

  label {
    margin-bottom: 0.3rem;
  }

  input,
  textarea {
    background-color: #fff8f0;
    font-size: 1.1rem;
    border: none;
    border-radius: 0.3rem;
    margin-bottom: 1rem;
    padding: 0.5rem;
  }
</style>
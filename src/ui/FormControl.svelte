<script>
    export let controlType = null;
    export let id;
    export let label;
    export let rows = null;
    export let value;
    export let type = "text";
</script>

<div class="form-control">
    <label for={id}>{label}</label>
    {#if controlType === 'textarea'}
        <textarea {id} {rows} {value} on:input/>
    {:else}
        <input {type} {id} {value} on:input/>
    {/if}
</div>
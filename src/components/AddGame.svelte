<script>
  import { createEventDispatcher } from "svelte";
  import Button from "../ui/Button.svelte";
  import FormControl from "../ui/FormControl.svelte";

  const dispatch = createEventDispatcher();
  let title = "";
  let creator = "";
  let url = "";
  let imageUrl = "";
  let description = "";
  let rating = "";

  const onSubmit = () => {
    dispatch("save", {
      id: `${Math.random()}_${Date.now()}`,
      title: title,
      creator: creator,
      url: url,
      imageUrl: imageUrl,
      description: description,
      rating: +rating
    });

    document.querySelector("form").reset();
  };
</script>

<form on:submit|preventDefault={onSubmit}>
  <fieldset>
    <legend>
      Add New Review
    </legend>
    <FormControl 
      id="title"
      value={title}
      on:input={(event) => title = event.target.value}
    >Game Title</FormControl>
      <FormControl 
      id="creator" 
      value={creator}
      on:input={(event) => creator = event.target.value}
    >Creator</FormControl>
      <FormControl 
      id="url" 
      value={url}
      on:input={(event) => url = event.target.value}
    >Creator URL</FormControl>
    <FormControl 
      id="image" 
      value={imageUrl}
      type="url"
      on:input={(event) => imageUrl = event.target.value}
    >Image URL</FormControl>
    <FormControl 
      id="description" 
      controlType="textarea"
      value={description}
      on:input={(event) => description = event.target.value}
    >Description</FormControl>
    <FormControl 
      id="rating" 
      value={rating}
      on:input={(event) => rating = event.target.value}
    >Rating</FormControl>
</fieldset>
  <Button>Add Review</Button>
</form>

<style>
  form {
    max-width: 30rem;
    margin: auto;
    display: flex;
    flex-direction: column;
  }
  fieldset {
    border: none;
  }

  legend {
    font-size: 2rem;
    font-weight: 600;
    text-align: center;
  }
</style>
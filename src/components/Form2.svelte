<script>
  import { createEventDispatcher } from "svelte";

  let dispatch = createEventDispatcher();

  let name;
  let color;
  const handleSubmit = () => {
    const food = {
      id: Math.random(),
      name: name,
      color: color,
    };

    dispatch("addFood", food);
    name = "";
    color = "";
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="color" bind:value={color} />
  <button type="submit">Add Food</button>
</form>

<style></style>

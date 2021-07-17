<script>
  import Announcement from "./components/Announcement.svelte";
  let fruits = [
    { name: "Apple", color: "red", amount: 5, id: 1 },
    { name: "Banana", color: "yellow", amount: 7, id: 2 },
    { name: "Grape", color: "purple", amount: 1, id: 3 },
  ];
  const deleteFruit = (id) => {
    console.log(id);
    fruits = fruits.filter((fruit) => fruit.id != id);
  };
</script>

<main>
  <Announcement />
  {#each fruits as fruit (fruit.id)}
    {#if fruit.amount >= 5}
      <div class="card">
        <h5>{fruit.name}</h5>
        <p>{fruit.color}</p>
        <button on:click={() => deleteFruit(fruit.id)}>Delete</button>
      </div>
    {:else}
      <p>whoops {fruit.name}</p>
    {/if}
  {:else}
    <p>there is no fruit on the basket</p>
  {/each}
</main>

<style>
  main {
    display: flex;
    align-items: center;
    flex-direction: column;
    font-family: "Comic Sans MS", cursive;
  }
  h1 {
    color: purple;
    font-family: "Comic Sans MS", cursive;
  }
  .card {
    border: 2px solid purple;
    border-radius: 5px;
    margin-bottom: 10px;
    min-width: 400px;
    padding: 5px;
  }
</style>

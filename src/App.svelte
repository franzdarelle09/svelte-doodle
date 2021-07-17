<script>
  import Form2 from "./components/Form2.svelte";
  let foods = [
    { id: 1, name: "Apple", color: "red" },
    { id: 2, name: "Banana", color: "yellow" },
  ];

  const addFood = (e) => {
    const food = e.detail;
    foods = [food, ...foods];
  };

  const deleteFruit = (id) => {
    console.log("delete");
    foods = foods.filter((food) => food.id != id);
  };
</script>

<main>
  <Form2 on:addFood={addFood} />
  {#each foods as food (food.id)}
    <div class="food-item">
      <h3>{food.name}</h3>
      <p>Color: {food.color}</p>
    </div>
    <button on:click={() => deleteFruit(food.id)}>Delete</button>
  {/each}
</main>

<style>
  .food-item {
    border: 2px solid gray;
    text-align: left;
    padding: 8px;
    margin-top: 20px;
    width: 100%;
  }
  main {
    display: flex;
    align-items: flex-start;
    flex-direction: column;
  }
</style>

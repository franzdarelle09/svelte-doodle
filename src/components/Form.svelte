<script>
  import { bind } from "svelte/internal";

  let name = "";
  let isCheck = true;
  let job = "hunter";
  let selected;
  let questions = [
    { id: 1, text: "What is your favorite color?" },
    { id: 2, text: "What is your favorite fruit?" },
  ];
</script>

<div class="form">
  <input type="text" bind:value={name} />
  {name}
  <br />
  <input type="checkbox" bind:checked={isCheck} /> <br />
  <input type="radio" bind:group={job} value={"assasin"} /> Assasin <br />
  <input type="radio" bind:group={job} value={"hunter"} /> Hunter <br />
  <input type="radio" bind:group={job} value={"swordsman"} /> Swordsman <br />

  <select bind:value={selected}>
    {#each questions as question}
      <option value={question}>{question.text}</option>
    {/each}
  </select>
</div>

<style>
  input {
    padding: 5px;
  }
</style>

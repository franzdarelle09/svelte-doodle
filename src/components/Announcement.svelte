<script>
  let show = true;
  const toggleAlert = () => {
    show = !show;
  };
  $: buttonText = show ? "Hide" : "Show";
  let warning = true;
</script>

{#if show}
  <div class="alert" class:warning>
    50% off all fruit. sign up for more fruit
  </div>
{/if}
<button on:click={toggleAlert}>{buttonText}</button>

<style>
  .alert {
    padding: 8px;
    font-size: 18px;
    background-color: darkseagreen;
    color: darkslategray;
    margin-bottom: 10px;
  }
  .warning {
    background-color: lightpink;
    color: darkred;
  }
</style>

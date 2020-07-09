<script>
  import Card from "./Card.svelte";
  export let images = [];
  console.log("images hola", images);
</script>

<style>
  .TimeLine {
    padding: 4em 0 0 0;
  }
</style>

<section class="TimeLine">
  <div class="Timeline-container">
    {#each images as image, id}
      <Card {...image} {id} />
    {:else}
      <p>Loading...</p>
    {/each}

  </div>
</section>

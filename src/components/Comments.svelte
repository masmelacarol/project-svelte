<script>
  import { afterUpdate } from "svelte";
  export let username = [];
  export let text;
  let comments = [
    {
      id: Date.now(),
      user: username,
      text: text
    }
  ];
  let comment = "";

  const addComment = e => {
    const msg = e.target.text.value;
    if (msg.length > 3) {
      const message = {
        id: Date.now(),
        user: "masmelacarol",
        text: msg
      };
      comments = [...comments, message];
      e.target.text.value = "";
    }
  };
</script>

<style>
  .Comments h3 {
    font-size: 14px;
    color: black;
    font-weight: bold;
    margin: 0;
    padding: 0;
  }
  .Comments span {
    font-size: 14px;
    margin: 0 0 0 0.5em;
    font-weight: normal;
    color: rgba(black, 0.9);
  }
  .Comments-add {
    padding: 1em 1em 1em 1em;
    border-top: 1px solid rgba(219, 219, 219, 0.8);
  }
  .Comments-add form {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Comments-content {
    padding: 0 1em 0.5em 1em;
  }
  .Comments-users {
    margin: 0 0 0.5em 0;
    display: flex;
    flex-direction: column;
  }

  input {
    border: solid 1px #e9e9e9;
    border-radius: 5px;
    color: #696969;
    border: 1px solid transparent;
    font-size: 12px;
    outline: none;
    width: 100%;
    display: flex;
  }
  button {
    border: none;
    color: #3897f0;
    font-size: 12px;
    outline: none;
    cursor: pointer;
  }
</style>

<section class="Comments">
  <div class="Comments-content">
    <div class="Comments-users">
      {#each comments as comment}
        {#if comment.user}
          <h3>{comment.user}</h3>
          <span>{comment.text}</span>
        {/if}
      {/each}
    </div>

    <div class="Comments-add">
      <form on:submit|preventDefault={addComment}>
        <input
          id="text"
          type="text"
          placeholder="Agregar comentario..."
          class="Comments-input"
          bind:value={comment} />
        <button type="submit">Post</button>
      </form>
    </div>
  </div>
</section>

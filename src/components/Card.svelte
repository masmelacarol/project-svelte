<script>
  import Comments from "./Comments.svelte";
  const fetchData = async () => {
    const response = await fetch("https://api.disneyapi.dev/characters");
    const data = await response.json();
    console.log("fetchData -> data", data);
    return data;
  };
  fetchData();
</script>

<div class="Card">
  <div class="Card-container">
    <header class="Card-header">
      <img
        src="https://avatars1.githubusercontent.com/u/22552150?s=400&u=f3e75b716d7411b061ff268f66dbb0f4b37a7bb4&v=4"
        alt="avatar-user" />
      <h2>
        Princess.disney
        <span>Bogotá, Colombia</span>
      </h2>
      <div class="Card-settings">
        <i class="fas fa-ellipsis-h" />
      </div>
    </header>
    <div class="Card-photo">
      <figure>
        <img src="" alt="img disney" />
      </figure>
    </div>
    <div class="Card-icons">
      <div class="Card-icons-first">
        <i class="fas fa-heart" />
        <i class="fas fa-paper-plane" />
      </div>
      <div class="Card-icons-second">
        <i class="fas fa-bookmark" />
      </div>
    </div>
    <Comments />
  </div>
</div>

<script>
  import { onMount } from "svelte";
  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";
  import Timeline from "../components/Timeline.svelte";
  import Sidebar from "../components/Sidebar.svelte";

  let images = [];
  const API = "https://api.disneyapi.dev/characters";
  onMount(async () => {
    const response = await fetch(API);
    images = await response.json();
    console.log("images", images);
  });
</script>

<Main>
  <Timeline {images} />
  <Sidebar />
</Main>

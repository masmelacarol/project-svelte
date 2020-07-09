<script context="module">
  export async function preload() {
    let images = [];
    const response = await this.fetch("https://api.disneyapi.dev/characters");
    images = await response.json();
    return { images };
  }
</script>

<script>
  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";
  import Timeline from "../components/Timeline.svelte";
  import Sidebar from "../components/Sidebar.svelte";
  export let images;
</script>

<svelte:head>
  <title>Disneytagram</title>
</svelte:head>

<Main>
  <Timeline {images} />
  <Sidebar />
</Main>

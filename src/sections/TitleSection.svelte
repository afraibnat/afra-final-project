<script>
  import TitleCard from "../lib/TitleCard.svelte";

  const title = "The Story of Black Business: Through a Pandemic Lens";
  const credit = `Photo from <a href="https://naacp.org/articles/black-america-and-coronavirus-pandemic"> NAACP</a>` ;
</script>

<div class="page-container">
  <TitleCard {title} {credit}/>
</div>

<style>
  .page-container {
    scroll-behavior: smooth;
    overflow-y: auto;
  }
</style>

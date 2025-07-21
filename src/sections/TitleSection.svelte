<script>
  import TitleCard from "../lib/TitleCard.svelte";
  import FullPageText from "../lib/FullPageText.svelte";

  const title = "The Story of Black Business: Through a Pandemic Lens";
  const subtitle = "How has Black business ownership varied across U.S. metropolitan areas over the past two decades, and what role did the COVID-19 pandemic play in accelerating or reversing these trends?";
  const credit = "Photo from";
</script>

<div class="page-container">
  <TitleCard {title} {credit} />
  <FullPageText {subtitle}/>
</div>

<style>
  .page-container {
    scroll-behavior: smooth;
    overflow-y: auto;
  }
</style>

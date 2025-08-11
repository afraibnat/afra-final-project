<script>
  import FullPageText from "../lib/FullPageText.svelte";

  const subtitle = `August is National Black Business Month. <br><br>Shop locally, share and collaborate with others, attend events, and advocate for change. <br><br>What can you do to support Black-owned businesses?`;
</script>

<div class="page-container">
  <FullPageText {subtitle}/>
</div>

<style>
  .page-container {
    scroll-behavior: smooth;
    overflow-y: auto;
  }
</style>

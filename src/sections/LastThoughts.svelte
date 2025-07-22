<script>
  import FullPageText from "../lib/FullPageText.svelte";

  const subtitle = `August is National Black Business Month. <br><br>Shop locally, share, collaborate, attend events, and advocate for Change. <br><br>What can you do to support Black-owned businesses?`;
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

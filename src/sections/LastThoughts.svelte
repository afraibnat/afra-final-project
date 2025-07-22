<script>
  import FullPageText from "../lib/FullPageText.svelte";

  const subtitle = "August is National Black Business Month. Shop locally, Share, Collaborate, Attend Events, and Advocate for Change. What can you do to support Black-owned businesses?";
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

<script>
  let { children } = $props();
</script>

<div class="text-container">
  {@render children()}
</div>

<style>
  .text-container {
    padding: 2rem;
    max-width: 700px;
    margin: 0 auto;
  }

  p {
    line-height: 1.6;
    font-size: 1.1rem;
  }
</style>

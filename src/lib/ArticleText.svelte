<script>
  let { children } = $props();
</script>

<div class="text-container">
  {@render children()}
</div>

<style>
  .text-container {
    max-width: 750px;
    margin: 0 auto;
    padding: 40px 24px;
    font-size: 21px;
    font-family: 'Helvetica Neue', 'Segoe UI', sans-serif;
    border-radius: 4px;
  }
</style>
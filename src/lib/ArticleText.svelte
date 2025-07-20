<script>
  let { children } = $props();
</script>

<div class="text-container">
  {@render children()}
</div>

<!-- <p>https://naacp.org/articles/black-america-and-coronavirus-pandemic</p> -->

<style>
  .text-container {
    max-width: 750px;
    margin: 0 auto;
    padding: 40px 24px;
    font-family: 'Helvetica Neue', 'Segoe UI', sans-serif;
    border-radius: 4px;
  }

  .text-container p {
    font-size: 18px;
    line-height: 1.8;
    color: #2e2e2e;
    margin-bottom: 1.5rem;
  }

  .text-container strong {
    font-size: 20px;
    font-weight: 700;
    display: block;
    color: #1a1a1a;
    margin-bottom: 1rem;
  }

  .text-container img {
    width: 100%;
    height: auto;
    margin-top: 20px;
    border-radius: 4px;
  }

  .text-container figcaption {
    font-size: 14px;
    color: #666;
    margin-top: 0.5rem;
    text-align: center;
  }
</style>

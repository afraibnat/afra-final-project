<script>
  export let subtitle;
</script>

<div class="research-question">
  <div class="content">
    <h2>{subtitle}</h2>
  </div>
</div>

<style>
  .research-question {
    height: 100vh;
    background-color: #0b1f2a;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    font-family: 'Inter', sans-serif;
    color: white;
  }

  .content {
    max-width: 40rem;
    margin: 0 auto;
  }

  h2 {
    font-size: 1.6rem;
    font-weight: 500; /* light */
    line-height: 1.6;
    margin: 0;
    white-space: pre-wrap; /* preserve line breaks if needed */
  }
</style>

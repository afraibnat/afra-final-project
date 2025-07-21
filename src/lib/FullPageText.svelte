<script>
  export let subsubtitle;
</script>

<div class="research-section">
  <div class="content">
    <h2>Research Question</h2>
    <p>{subsubtitle}</p>
  </div>
</div>

<style>
  .research-section {
    height: 100vh;
    background-color: #44c4a1;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    font-family: "Inter", sans-serif;
  }

  .content {
    max-width: 700px;
    background-color: rgba(0, 0, 0, 0.4);
    padding: 2rem;
    border-radius: 1rem;
  }

  h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }

  p {
    font-size: 1.3rem;
  }
</style>

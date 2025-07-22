<script>
  export let title;
  export let credit;
</script>

<div class="title-card">
  <div class="title-text">
    <h1>{title}</h1>
      <p class="credit-text">{@html credit}</p>
  </div>
</div>

<style>
  .title-card {
    height: 100vh;
    background-image: url("/naacp.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 3rem;
    font-family: "Inter", sans-serif;
    color: #ffffff;
  }

  .title-text {
    max-width: 800px;
    text-align: left;
    color: #ffffff;
    font-family: "Inter", sans-serif;
  }

  h1 {
    font-size: 3.5rem;
    font-weight: 800;
    margin-bottom: 1rem;
    line-height: 1.2;
  }

  .credit {
    font-size: 1rem;
    font-weight: 300;
    color: #ddd;
  }

</style>

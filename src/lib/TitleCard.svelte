<script>
  export let title;
  export let subtitle;
</script>

<div class="title-card">
  <div class="content">
    <h1>{title}</h1>
    <p>{subtitle}</p>
  </div>
</div>

<style>
  .title-card {
    height: 100vh;
    background-image: url('/naacp.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    font-family: "Inter", sans-serif;
    color: white;
  }

  .content {
    max-width: 700px;
    background-color: rgba(0, 0, 0, 0.5);
    padding: 2rem;
    border-radius: 1rem;
  }

  h1 {
    font-size: 3rem;
    margin: 0;
  }

  p {
    font-size: 1.3rem;
    margin-top: 1rem;
  }
</style>

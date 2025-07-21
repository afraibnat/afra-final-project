<script>
  export let image;
</script>

<div class="background-container">
  <div class="background-image" style="background-image: url({image});"></div>
  <div class="overlay-content">
    <slot />
  </div>
</div>

<style>
  .background-container {
    position: sticky;
    top: 0;
    height: 100vh;
    width: 100%;
    overflow: hidden;
    z-index: 0;
  }

  .background-image {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    transition: background-image 1s ease-in-out;
  }

  .overlay-content {
    position: relative;
    text-align: center;
    color: white;
    text-shadow: 0 2px 6px rgba(0, 0, 0, 0.6);
    padding: 3rem;
    z-index: 1;
  }
</style>

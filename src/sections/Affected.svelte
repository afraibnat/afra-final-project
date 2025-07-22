<script>
  import { fade, fly } from "svelte/transition";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  let imageIndex = 0;

  const images = ["affected.jpg"];
  const captions = [
    `Two individuals wearing masks are pictured, one to purchase equipment. <a href="https://www.brookings.edu/articles/who-are-the-workers-already-impacted-by-the-covid-19-recession/"> Source</a>`,
  ];

  const options = {
    threshold: [0.85, 0.95],
  };

  const setImageIndex = (index) => (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
        imageIndex = index;
      }
    });
  };
</script>


<Scroller layout="right">
    {#snippet sticky()}
    <div class="image-container">
      {#key imageIndex}
        <img
          class="duck-img"
          src={images[imageIndex]}
          alt="Scroll-based image"
          in:fly={{ y: 200, duration: 1000 }}
        />
      {/key}
      <div class="caption" transition:fade>
        {@html captions[imageIndex]}
      </div>
    </div>
  {/snippet}

    {#snippet scrolly()}
        <ObservedArticleText callback={setImageIndex(0)} {options}>
            <h2>Why were Black-owned Businesses Tremondously Affected?</h2>
            <p>
                Black businesses were geographically located in COVID-19
                hotspots, racial <a
                    href="https://www.aljazeera.com/economy/2020/8/7/us-why-were-black-owned-businesses-the-hardest-hit-by-pandemic"
                    target="_blank"
                    rel="noopener noreferrer">disparities</a
                > in receiving federal relief funds, and general funding gaps occurring
                pre-pandemic.
            </p>
        </ObservedArticleText>
    {/snippet}
</Scroller>

<style>
  .image-container {
    text-align: center;
    margin-bottom: 1rem;
  }

  .duck-img {
    margin: 0 auto;
    display: block;
    max-width: 450px;
    height: 100%;
  }

  .caption {
    font-size: 14px;
    color: #444;
    margin-top: 0.5rem;
    max-width: 420px;
    margin-left: auto;
    margin-right: auto;
    line-height: 1.4;
  }
</style>

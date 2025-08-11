<script>
  import { fade, fly } from "svelte/transition";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  let imageIndex = 0;

  const images = ["march-april.jpg"];
  const captions = [
    `A group wearing masks are pictured. <a href="https://www.pewresearch.org/short-reads/2021/03/09/black-americans-stand-out-for-their-concern-about-covid-19-61-say-they-plan-to-get-vaccinated-or-already-have/"> Source</a>`,
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

<Scroller layout="left">
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
      <h2>During the months of March and April 2020...</h2>
      <p>
        Average business earnings declined sharply across all groups. Black business owners saw an 11% drop, Asian-owned businesses declined by 15%
        for Asian businesses, Latinx businesses by 7%, and White-owned businesses by 2%.
      </p>
      <p>
        Losses for minority business owners were <a
          href="https://advocacy.sba.gov/wp-content/uploads/2022/08/Report_COVID-and-Racial-Disparities_508c.pdf"
          target="_blank"
          rel="noopener noreferrer">disproportionately felt.</a
        > While the overall loss in business earnings averaged 17%, Black-owned businesses experienced a significantly higher decline of 28%.      </p>
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

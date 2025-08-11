<script>
  import { fade, fly } from "svelte/transition";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  let imageIndex = 0;

  const images = ["covid-business.jpg", "golden-age.jpg", "daniel-speed.jpg"];
  const captions = [
    `A masked tailor working during the COVID-19 pandemic. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
    `The rise of Black-owned businesses during the Golden Age, 1900–1930. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
    `Daniel Speed, a grocer who helped fund civil rights efforts in the 1950s and 60s. <a href="https://www.historypin.org/en/explore/geo/37.77493,-122.419416,12/bounds/37.702303,-122.493402,37.847486,-122.34543/paging/1/pin/1139634"> Source</a>`,
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

<div>
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
        <p>
          <strong
            >With the economic fallout during the COVID-19 pandemic in 2020,</strong
          >
          Black Americans, the most deeply impacted racial group, saw a 41%
          decline in business ownership, along with 440,000
          <a
            href="https://www.bloomberg.com/news/articles/2020-06-08/black-business-owners-suffer-41-drop-in-covid-19-lockdowns"
            target="_blank"
            rel="noopener noreferrer">businesses collapsing.</a
          >
          Furthermore, they faced an unemployment rate of 16.8%.
        </p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(1)} {options}>
        <p>
          <strong
            >However, this economic collapse was not an isolated event. it
            reflected centuries of long-term systemic civil and economic
            injustices.</strong
          >
        </p>
        <p>
          For decades, Jim Crow laws barred Black Americans from white-owned
          restaurants, universities, churches, and businesses, forces designed
          to limit opportunities, leading many to rely on self-sufficiency.
        </p>
        <p>
          As a result, there came the <a
            href="https://blackcreative.co/the-origins-of-black-owned-businesses-and-why-they-matter-today/"
            target="_blank"
            rel="noopener noreferrer">“Golden Age”</a
          > of Black-owned businesses from 1900 to 1930. During this time, the number
          of Black-owned companies doubled from 20,000 to 40,000 between 1900 and
          1915.
        </p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(2)} {options}>
        <p>
          <strong>These independent black-owned businesses played a significant role in
          financing civil rights protests during the 1950s and 60s. </strong></p>
        <p>Grocery
          store owner <a
            href="https://blackcreative.co/the-origins-of-black-owned-businesses-and-why-they-matter-today/"
            target="_blank"
            rel="noopener noreferrer">Daniel Speed</a
          > bankrolled a bus boycott similar to the Montgomery boycott, and his shop
          served as a meeting ground for black leaders.
        </p>
      </ObservedArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  .image-container {
    text-align: center;
    margin-bottom: 1rem;
  }

  .duck-img {
    margin: 0 auto;
    display: block;
    max-width: 400px;
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

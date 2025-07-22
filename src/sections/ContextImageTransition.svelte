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
            With the economic fallout during the COVID-19 pandemic in 2020, 
            <a href="https://en.wikipedia.org/wiki/National_Negro_Business_League" target="_blank" rel="noopener noreferrer">
    the most deeply impacted racial group were Black-owned businesses,</a>
            seeing a 41% decline in number, along with the collapse of 440,000.
            Furthermore, Black Americans faced an unemployment rate of 16.8%.
        </p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(1)} {options}>
        <p>
          But this collapse was a result of long-term civil and economic
          justices. Black Americans were not allowed in white restaurants,
          universities, churches, or businesses due to Jim Crow laws and
          segregation, barriers meant to keep Black people from having the same
          opportunities from white people, leading to many starting their own to
          rely on self-sufficiency.
        </p>
        <p>
          As a result, there came the <a href="https://blackcreative.co/the-origins-of-black-owned-businesses-and-why-they-matter-today/" target="_blank" rel="noopener noreferrer">“Golden Age”</a> of Black-owned businesses
          from 1900 to 1930. The number of Black-owned companies doubled from
          20,000 to 40,000 between 1900 and 1915, according to the National
          Negro Business League.
        </p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(2)} {options}>
        <p>
          Independent black-owned businesses played a significant role in
          financing civil rights protests during the 1950s and 60s. Grocery
          store owner <a href="https://blackcreative.co/the-origins-of-black-owned-businesses-and-why-they-matter-today/" target="_blank" rel="noopener noreferrer">Daniel Speed</a> bankrolled a bus boycott similar to the
          Montgomery boycott, and his shop served as a meeting ground for black
          leaders.
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

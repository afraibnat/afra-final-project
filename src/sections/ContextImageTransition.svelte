<script>
  import { fade, fly } from "svelte/transition";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  let imageIndex = 0;

  const images = ["covid-business.jpg", "golden-age.jpg", "daniel-speed.jpg"];

  const options = {
    threshold: [0.85, 0.95]
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
      <div>
        {#key imageIndex}
          <img
            class="duck-img"
            src={images[imageIndex]}
            alt="Scroll-based image"
            in:fly={{ y: 200, duration: 1000 }}
            out:fade
          />
        {/key}
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText callback={setImageIndex(0)} {options}>
        <p><strong>
                    With the economic fallout during the COVID-19 pandemic in
                    2020, the most deeply impacted racial group were Black-owned
                    businesses, seeing a 41% decline in number, along with the
                    collapse of 440,000. Furthermore, Black Americans faced an
                    unemployment rate of 16.8%.
                </strong></p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(1)} {options}>
        <p>But this collapse was a result of long-term civil and economic
                justices. Black people were not allowed in white restaurants,
                universities, churches, or businesses due to Jim Crow laws and
                segregation, barriers meant to keep Black people from having the
                same opportunities from white people, leading to many starting
                their own to rely on self-sufficiency.</p>
        <p>As a result, there came the “Golden Age” of Black-owned
                businesses from 1900 to 1930. The number of Black-owned
                companies doubled from 20,000 to 40,000 between 1900 and 1915,
                according to the National Negro Business League.</p>
      </ObservedArticleText>

      <ObservedArticleText callback={setImageIndex(2)} {options}>
        <p>Independent black-owned businesses played a significant role in
                financing civil rights protests during the 1950s and 60s.
                Grocery store owner Daniel Speed bankrolled a bus boycott
                similar to the Montgomery boycott, and his shop served as a
                meeting ground for black leaders.</p>
      </ObservedArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  .duck-img {
    margin: 0 auto;
    display: block;
    max-width: 400px;
    height: auto;
  }
</style>

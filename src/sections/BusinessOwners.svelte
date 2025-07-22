<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="center">
  {#snippet sticky()}
    <div class="background-container">
      <img src="naacp.jpg" alt="NAACP" />
    </div>
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
      <div class="text-box">
        <h2>Who are Black Business Owners?</h2>
        <p>
          <strong>More Likely to be Men than Women.</strong> Some 54% of Black-owned
          firms in 2022 had men as their majority owners, while 39% had women as
          their majority owners.
        </p>
        <p>
          <strong>A Greater Percentage are Middle-Aged.</strong> Half of Black or
          African American business owners who reported their age group were ages
          35 to 54 in 2022.
        </p>
        <p>
          <strong>A Majority have a College Degree.</strong> Among owners who reported
          their highest level of education completed, 27% had a bachelor’s degree
          and 34% had a graduate or professional degree beyond a bachelor’s in 2022.
        </p>
      </div>
      <div class="chart-footnote">
        Source: <a href="https://www.pewresearch.org/short-reads/2025/02/12/a-look-at-black-owned-businesses-in-the-us/">Pew Research Center</a>
      </div>
    </ArticleText>
  {/snippet}
</Scroller>

<!-- <Scroller layout="center">
  {#snippet sticky()}
    <StickyBackground image="/naacp.jpg" />
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
      <div class="text-box">
        <p>
          Supporting Black-owned businesses is essential to closing the racial
          wealth gap.
        </p>
        <p>
          Black people make up 12.4% of the American population, but possess
          only 2.4% of the nation’s wealth.
        </p>
        <p>
          While the amount of Black-owned businesses increased from 2.2% in 2017
          to 3.3% in 2022, this representation is far below Black Americans’
          14.4% share.
        </p>
      </div>
    </ArticleText>
  {/snippet}
</Scroller> -->

<style>
  .background-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    overflow: hidden;
  }
  .background-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .text-box {
    max-width: 600px;
    background-color: rgba(0, 0, 0, 0.5); /* semi-transparent */
    color: white;
    padding: 2rem;
    border-radius: 0.5rem;
    font-family: sans-serif;
    line-height: 1.6;
    text-align: left;
    position: relative;
    z-index: 1; /* ensures it's above the background */
    margin: 2rem auto;
  }

  .chart-footnote {
    font-size: 12px;
    color: #666;
    text-align: right;
    margin-top: 8px;
    line-height: 1.4;
  }
</style>

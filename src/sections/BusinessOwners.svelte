<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="center">
  {#snippet sticky()}
    <img src="naacp.jpg" alt="KWK rubber duck!" />
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
      <div class="text-box">
        <h2>Who are Black Business Owners?</h2>
        <p><strong>More Likely to be Men than Women</strong></p>
        <p><strong>A Greater Percentage are Middle-Aged</strong></p>
        <p><strong>A Majority have a College Degree</strong></p>
      </div>
    </ArticleText>
  {/snippet}
</Scroller>

<Scroller layout="center">
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
</Scroller>

<style>
  .text-box {
    max-width: 600px;
    background-color: rgba(95, 99, 168, 0.6);
    color: white;
    padding: 2rem;
    border-radius: 0.5rem;
    font-family: sans-serif;
    line-height: 1.6;
    text-align: left;
  }
</style>

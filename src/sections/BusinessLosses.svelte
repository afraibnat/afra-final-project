<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
</script>

<Scroller layout="left">
  {#snippet sticky()}
    <img class="duck-img" src="duck.png" alt="KWK rubber duck!" />
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
      <h2>During the months of March and April 2020...</h2>
      <p>
        Average business earnings dropped by 11 percent for Black business
        owners, 15 percent for Asian businesses, 7 percent for Latinx, and 2
        percent for white
      </p>
      <p>
        Losses for minority business owners were disproportionately felt. Losses
        of business earnings were 17 percent for all business owners, but 28
        percent for Black businesses.
      </p>
    </ArticleText>
  {/snippet}
</Scroller>

<style>
  .duck-img {
    width: 25%;
    margin: 0px auto;
  }
</style>

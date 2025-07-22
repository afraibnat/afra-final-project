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
        Average business earnings dropped by 11% for Black business
        owners, 15% for Asian businesses, 7% for Latinx, and 2% for white.
      </p>
      <p>
        Losses for minority business owners were <a href="https://advocacy.sba.gov/wp-content/uploads/2022/08/Report_COVID-and-Racial-Disparities_508c.pdf" target="_blank" rel="noopener noreferrer">disproportionately felt.</a> Losses
        of business earnings were 17% for all business owners, but 28% for Black businesses.
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

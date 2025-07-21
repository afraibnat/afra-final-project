<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
</script>

<Scroller layout="center">
  {#snippet sticky()}
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
        Although 440,000 African-American businesses had collapsed, 
        a partial rebound was seen in the next months, with a 
        little over 280,000 black businesses not operating in May 2020, 
        the number accounting for 26% lower than in February 2020, 
        the largest drop for any racial group, creating long-term consequences for savings and wealth accumulation.
    </ArticleText>

    <ArticleText>
      The Small Business Administration (SBA) had to prioritize loans 
      for minority businesses and underserved communities in 2020 - 2021.
    </ArticleText>

    <ArticleText>
        Overall, black-owned businesses rebounded strongly from the pandemic. 
        Businesses were hit hard in the beginning, resulting in a depletion of 
        new applications from January to April 2020. In July, application rates 
        recovered, reaching numbers higher than prior to the pandemic. 
        In the period of March 2020 to March 2021, new business applications rose by 73.9%.
    </ArticleText>
  {/snippet}
</Scroller>

<style>

</style>

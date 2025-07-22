<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<Scroller layout="center">
  {#snippet sticky()}
  {/snippet}

  {#snippet scrolly()}
  <ArticleText>
        <p>The pandemic caused an unprecedented economic shock.</p>
        <p>Despite significant growth in Black-owned businesses, disparities remian stark.
        Black entrepreneurs face challenges such as undercapitalization, limited access
        to funding, and lower approval rates for loans compared to white-owned businesses.
        While the partial rebound and continued growth is encouraging, ongoing commitment form
        government agencies and communities is critical to building a inclusive 
        entrepreneurial world that benefits Black business owners and the broader economy.</p>
    </ArticleText>
  {/snippet}
</Scroller>

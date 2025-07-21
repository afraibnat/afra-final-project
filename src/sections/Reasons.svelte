<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="right">
  {#snippet sticky()}
    <StickyBackground image="/naacp.jpg">
        <h1>Business Losses</h1>
    </StickyBackground>
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
        <h2>Why were they so affected?</h2>
        <p>Black businesses were geographically located in COVID-19 hotspots, 
            racial disparities in receiving federal relief funds, and 
            general funding gaps occurring pre-pandemic.</p>
    </ArticleText>
  {/snippet}
</Scroller>

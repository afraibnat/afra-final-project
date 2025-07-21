<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText2 from "../lib/ArticleText2.svelte";
    import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="left">
  {#snippet sticky()}
    <StickyBackground image="/naacp.jpg">
      <h1>Black Business Ownership</h1>
    </StickyBackground>
  {/snippet}

  {#snippet scrolly()}
    <ArticleText2>
      <p>This is the start of the story...</p>
      <p>continues</p>
      <p>and more</p>
    </ArticleText2>
  {/snippet}
</Scroller>

<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="left">
  {#snippet sticky()}
    <StickyBackground image="/naacp.jpg">
    </StickyBackground>
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
      <h2>Who are Black Business Owners?</h2>
      <p><strong>More Likely to be Men than Women</strong></p>
      <p><strong>A Greater Percentage are Middle-Aged</strong></p>
      <p><strong>A MAjority have a College Degree</strong></p>
    </ArticleText>
  {/snippet}
</Scroller>

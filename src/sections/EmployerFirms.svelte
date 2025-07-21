<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import StickyBackground from "../lib/StickyBackground.svelte";
</script>

<Scroller layout="right">
    {#snippet sticky()}
        <h2>Employer Firms by Race/Ethnicity</h2>
        <img src="employer-firms.png" alt="KWK rubber duck!" />
        <div class="chart-footnote">
            This chart points out the number of employer firms, not non-employer
            firms. For example, the District of Columbia (Washington D.C.) has a
            greater Black population of 43.3%, but 1,866 Black employer firms.
            This is because, despite a bustling environment of Black-owned
            businesses, a large number are non-employer firms rather than
            employer firms. (need source)
            <br />
            Source: <a href="https://example.com">U.S. Census Bureau</a>
        </div>
    {/snippet}
</Scroller>

<style>
    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }
</style>

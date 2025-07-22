<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h2>Recovery</h2>
            <img src="business-operations.png" alt="KWK rubber duck!" />
            <div class="chart-footnote">
                Source: <a
                    href="https://www.brookings.edu/articles/new-data-shows-small-businesses-in-communities-of-color-had-unequal-access-to-federal-covid-19-relief/"
                    >Brookings</a
                >
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <p>
                    Recently in February 2023, these rates remain high,
                    conveying recovery. Industries that were struggling during
                    the pandemic and were highly-concentrated in black
                    businesses are now flourishing (Accommodations, Food
                    Service, Construction, Professional, and Health Services).
                </p>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }
</style>

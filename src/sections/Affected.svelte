<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<Scroller layout="right">
    {#snippet sticky()}
        <img class="duck-img" src="duck.png" alt="KWK rubber duck!" />
    {/snippet}

    {#snippet scrolly()}
        <ArticleText>
            <h2>Why were Black-owned Businesses Tremondously Affected?</h2>
            <p>
                Black businesses were geographically located in COVID-19
                hotspots, racial <a
                    href="https://www.aljazeera.com/economy/2020/8/7/us-why-were-black-owned-businesses-the-hardest-hit-by-pandemic"
                    target="_blank"
                    rel="noopener noreferrer">disparities</a
                > in receiving federal relief funds, and general funding gaps occurring
                pre-pandemic.
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

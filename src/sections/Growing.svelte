<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img src="business-operations.png" alt="KWK rubber duck!" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h2>Recovery</h2>
                <p>Recently in February 2023, these rates remain high, conveying recovery.</p>

                <p>As you can see, the industries that were struggling during the pandemic 
                    and were highly-concentrated in black businesses are now flourishing (Accommodations, Food Service, Construction, Professional, and Health Services).</p>
            </ArticleText>

        {/snippet}
    </Scroller>
</div>

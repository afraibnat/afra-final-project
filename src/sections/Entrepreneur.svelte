<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="duck-img" src="everett-sands.jpg" alt="KWK rubber duck!" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <p>Black entrepreneurism ranked high. On average, 
                    380 out of every 100,000 Black adults became 
                    new entrepreneurs during 2020, up from 240 from the past two years.</p>
            </ArticleText>
            <ArticleText>Everett Sands, CEO of Lendisty, one of the largest Black-owned small-business leaders, saw inquiries from Black customers interested in starting businesses. Those who reached out were interested in opening daycare centers or started delivery service.
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .duck-img {
        width: 25%;
        margin: 0px auto;
    }
</style>

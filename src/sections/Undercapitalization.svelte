<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="duck-img" src="duck.png" alt="KWK rubber duck!" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <p>It’s important to point out the undercapitalization of Black businesses 
                    in regards to the U.S metro area’s Black populations. If the number of Black 
                    businesses matched population size and employees per firm matched the average business, 
                    it would create 206,441 jobs.
                </p>
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

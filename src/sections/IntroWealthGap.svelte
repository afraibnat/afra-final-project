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
                <p>Supporting Black-owned businesses is essential to closing the racial wealth gap.</p>
                <p>Black people make up 12.4% of the American population, but possess only 2.4% of the nation’s wealth.</p>
                <p>While the amount of Black-owned businesses increased from 2.2% in 2017 to 3.3% in 2022, 
                this representation is far below Black Americans’ 14.4% share.</p>
                <p>For decades, there has been an uneven landscape of American business ownership for Black entrepreneurs. 
                    It was only until 1954 when the Bureau of Labor Statistics reported employment rates by race, 
                    of white or nonwhite.</p>
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

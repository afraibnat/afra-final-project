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
                <h2>COVID Disruption</h2>
                <p>
                    The past few years pre-COVID revealed steady growth for
                    Black-owned businesses in the United States.
                </p>
                <p>
                    Between 2017 and 2020, the <a
                        href="https://www.brookings.edu/articles/who-is-driving-black-business-growth-insights-from-the-latest-data-on-black-owned-businesses/#:~:text=Between%202017%20and%202020%2C%20the,an%2011%25%20increase%20since%202017
"
                        target="_blank"
                        rel="noopener noreferrer">average yearly growth rate</a
                    >
                    in the of black owned business was 4.2%, 20 more times the overall
                    business growth rate of 0.18%. It had the greatest growth between
                    2018 and 2019, when it rose by 8%, but declined to 4.7% between
                    2019 and 2020, representing the impact of the pandemic.
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

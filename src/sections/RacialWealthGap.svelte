<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="page-wrapper">
    <div class="background-color" aria-hidden="true"></div>
    <Scroller layout="center">
        {#snippet sticky()}{/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <div class="text-box">
                    <p>
                        Supporting Black-owned businesses is essential to
                        closing the racial wealth gap.
                    </p>
                    <p>
                        Black people make up 12.4% of the American population,
                        but possess only 2.4% of the nation’s wealth.
                    </p>
                    <p>
                        While the amount of Black-owned businesses increased
                        from 2.2% in 2017 to 3.3% in 2022, this representation
                        is far below Black Americans’ 14.4% share.
                    </p>
                </div>
                <div class="chart-footnote">
                    Source: <a
                        href="https://www.africanamericanchambersa.org/the-impact-of-covid-19-on-african-american-owned-businesses/"
                        >African American Chambers</a
                    >
                </div>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .background-color {
        position: absolute;
        inset: 0;
        background: #2e0953;
        opacity: 0.8;
        z-index: 0;
    }

    .page-wrapper {
        position: relative;
        min-height: 100vh;
        overflow: hidden; /* if background overflows */
    }

    .text-box {
        max-width: 600px;
        background-color: #061922; /* semi-transparent */
        color: white;
        padding: 2rem;
        border-radius: 0.5rem;
        font-family: sans-serif;
        line-height: 1.6;
        text-align: left;
        position: relative;
        z-index: 1; /* ensures it's above the background */
        margin: 2rem auto;
    }

    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }
</style>

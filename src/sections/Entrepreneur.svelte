<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img
                class="duck-img"
                src="everett-sands.jpg"
                alt="KWK rubber duck!"
            />
            <div class="chart-footnote">
                Source: <a
                    href="https://inglewoodtoday.com/featured/celebrating-financial-literacy-month-lendistry-ceo-everett-sands-pioneers-with-scientific-brilliance/"
                    >Economic Policy Institute</a
                >
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <p>
                    Black entrepreneurism ranked high. On average,
                    <a
                        href="https://www.latimes.com/politics/story/2021-06-28/pandemic-silver-lining-black-owned-business-startups-surge-to-25-year-high"
                        target="_blank"
                        rel="noopener noreferrer"
                        >380 out of every 100,000 Black adults</a
                    >
                    became new entrepreneurs during 2020, up from 240 from the past
                    two years.
                </p>
                <br />
                <br />
                <br />
                <p>
                    Everett Sands, CEO of Lendisty, one of the largest
                    Black-owned small-business leaders, saw inquiries from Black
                    customers interested in starting businesses. Those who
                    reached out were interested in opening daycare centers or
                    started delivery service.
                </p>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .duck-img {
        margin: 0 auto;
        display: block;
        max-width: 400px;
        height: 100%;
    }
    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }
</style>

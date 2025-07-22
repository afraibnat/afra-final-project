<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
</script>

<div class="page-wrapper">
    <div class="background-color" aria-hidden="true"></div>
    <Scroller layout="center">
        {#snippet sticky()}{/snippet}

        {#snippet scrolly()}
            <div class="text-box">
                <ArticleText>
                    Although 440,000 African-American businesses had collapsed,
                    a partial rebound was seen in the next months, <a
                        href="https://www.africanamericanchambersa.org/the-impact-of-covid-19-on-african-american-owned-businesses/"
                        target="_blank"
                        rel="noopener noreferrer"
                        >with a little over 280,000 black businesses not
                        operating in May 2020,</a
                    >
                    the number accounting for 26% lower than in February 2020, the
                    largest drop for any racial group, creating long-term consequences
                    for savings and wealth accumulation.
                </ArticleText>

                <ArticleText>
                    The Small Business Administration (SBA) had to <a
                        href="https://www.latimes.com/politics/story/2021-06-28/pandemic-silver-lining-black-owned-business-startups-surge-to-25-year-high"
                        target="_blank"
                        rel="noopener noreferrer"
                        >prioritize loans for minority businesses and
                        underserved communities in 2020 - 2021.</a
                    >
                </ArticleText>

                <ArticleText>
                    Overall, black-owned businesses rebounded strongly from the
                    pandemic. Businesses were hit hard in the beginning,
                    resulting in a depletion of new applications from January to
                    April 2020. In July, <a
                        href="https://www.brookings.edu/articles/who-is-driving-black-business-growth-insights-from-the-latest-data-on-black-owned-businesses/#:~:text=Between%202017%20and%202020%2C%20the,an%2011%25%20increase%20since%202017"
                        target="_blank"
                        rel="noopener noreferrer"
                        >application rates recovered, reaching numbers higher
                        than prior to the pandemic.</a
                    >
                    In the period of March 2020 to March 2021, new business applications
                    rose by 73.9%.
                </ArticleText>
            </div>
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
</style>

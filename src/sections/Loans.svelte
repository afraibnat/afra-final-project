<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["employer-firms.png"];
    const captions = [
        `A masked tailor working during the COVID-19 pandemic. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
    ];

    const options = {
        threshold: [0.85, 0.95],
    };

    const setImageIndex = (index) => (entries) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
                imageIndex = index;
            }
        });
    };
</script>

<Scroller layout="right">
    {#snippet sticky()}
        <h2>Employer Firms By Race/Ethnicity</h2>
        <div class="image-container">
            {#key imageIndex}
                <img
                    src={images[imageIndex]}
                    alt="Scroll-based image"
                    in:fly={{ y: 200, duration: 1000 }}
                />
            {/key}
            <div class="chart-footnote">
                Source: <a href="hhttps://blackwealthdata.org/explore/business#BOW-02">Black Wealth Data Center</a>
            </div>
        </div>
    {/snippet}

    {#snippet scrolly()}
        <ArticleText>
            <p>
                Up to $659 billion was given in forgivable loans of government
                funding to cover expenses such as mortgage, rent, and utilities
                for small businesses as part of the Paycheck Protection Program
                (PPP), an inclusion of the CARES Act to avoid closures and
                overall economic crisis as a result of the pandemic.
            </p>
            <br />
            <p>
                Unfortunately, the distribution of the loans across the country
                was not equal. <a href="https://www.brookings.edu/articles/new-data-shows-small-businesses-in-communities-of-color-had-unequal-access-to-federal-covid-19-relief/" target="_blank" rel="noopener noreferrer">The first round gave relief to only employer firms.</a>
                This disregarded a large percentage of Black-owned
                businesses, 95% of which are nonemployer firms compared to the
                78% of white-owned firms.
            </p>
        </ArticleText>

        <ObservedArticleText callback={setImageIndex(0)} {options}>
            <p>
                This chart points out the number of employer firms, not
                non-employer firms. For example, the District of Columbia
                (Washington D.C.) has a greater Black population of 43.3%, but
                1,866 Black employer firms. This is because, despite a bustling
                environment of Black-owned businesses, <a href="https://www.census.gov/quickfacts/fact/table/DC/PST045223" target="_blank" rel="noopener noreferrer"> large number are
                non-employer firms rather than employer firms.</a>
            </p>
        </ObservedArticleText>
    {/snippet}
</Scroller>

<Scroller layout="center">
  {#snippet sticky()}
  {/snippet}

  {#snippet scrolly()}
    <ArticleText>
        Majority-Black neighborhoods in Washington D.C. <a href="https://www.brookings.edu/articles/new-data-shows-small-businesses-in-communities-of-color-had-unequal-access-to-federal-covid-19-relief/" target="_blank" rel="noopener noreferrer">waited longer for PPP loans.</a> 
        Black-owned businesses are far less likely to be approved for loans, 
        and Black business owners are <a href="https://nul.org/news/black-owned-businesses-face-significant-obstacles-anti-racial-justice-efforts-are-making-them" target="_blank" rel="noopener noreferrer">more likely to pull from their personal savings for business expenses.</a>
    </ArticleText>

    <ArticleText>
      Over 50% of black-owned businesses applied for PPP,  <a href="https://www.africanamericanchambersa.org/the-impact-of-covid-19-on-african-american-owned-businesses/" target="_blank" rel="noopener noreferrer">but only 20.3%
            have been granted the full amount.</a> As for Economic Injury Disaster
            Loans, 61.1% of African-American-owned businesses requested, but
            only 15% received the full amount. In comparison, 44.3% of white
            Americans applied, and 42.8% received the full amount.
    </ArticleText>
  {/snippet}
</Scroller>

<style>
    .image-container {
        text-align: center;
        margin-bottom: 1rem;
    }
    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }
</style>

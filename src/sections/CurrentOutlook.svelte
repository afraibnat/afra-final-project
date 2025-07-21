<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["parity.png", "loan-apps.png"];
    const captions = [
        `A masked tailor working during the COVID-19 pandemic. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
        `The rise of Black-owned businesses during the Golden Age, 1900–1930. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
        `Daniel Speed, a grocer who helped fund civil rights efforts in the 1950s and 60s. <a href="https://www.historypin.org/en/explore/geo/37.77493,-122.419416,12/bounds/37.702303,-122.493402,37.847486,-122.34543/paging/1/pin/1139634"> Source</a>`,
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

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h2>Current</h2>
            <div class="image-container">
                {#key imageIndex}
                    <img
                        class="duck-img"
                        src={images[imageIndex]}
                        alt="Scroll-based image"
                        in:fly={{ y: 200, duration: 1000 }}
                    />
                {/key}
                <div class="caption" transition:fade>
                    {@html captions[imageIndex]}
                </div>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={setImageIndex(0)} {options}>
                <p>
                    The top ten metro areas by ratio of Black businesses to Black residents 
                    show that the areas closest to achieving parity (Black business ownership 
                    rate equal to the share of Black residents in the metro area) tend to have 
                    smaller numbers of Black-owned businesses. Portland, Maine, Fresno, Calif, 
                    and Santa Rosa, California, have fewer than 300 Black owned employer firms. 
                    On the other hand, places such as Washington D.C. have a high percentage of 
                    Black population and Black-owned businesses.
                </p>
            </ObservedArticleText>

            <ObservedArticleText callback={setImageIndex(1)} {options}>
                <p>
                    The number and share of Small Business Administration (SBA) and 504 loans have gone to Black-owned businesses has more than doubled since 2020 due to the Biden Administration.
                </p>
                <p>
                    But, despite the growing rate of 30% during 2021, Black-owned businesses with at least two employees represent 2.5% of all businesses in the United States. 
                </p>
                <p>Clearly, federal funding needs to be transformed and give opportunities for Black-owned businesses to flourish.</p>
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .image-container {
        text-align: center;
        margin-bottom: 1rem;
    }

    .duck-img {
        margin: 0 auto;
        display: block;
        max-width: 400px;
        height: auto;
    }

    .caption {
        font-size: 14px;
        color: #444;
        margin-top: 0.5rem;
        max-width: 420px;
        margin-left: auto;
        margin-right: auto;
        line-height: 1.4;
    }
</style>

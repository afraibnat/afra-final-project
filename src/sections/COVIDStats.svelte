<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["covid-19-disruption.jpg"];
    const captions = [
        `At this restaurant, a sign indicates social distancing. <a href="https://www.aljazeera.com/economy/2020/8/7/us-why-were-black-owned-businesses-the-hardest-hit-by-pandemic"> Source</a>`,
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
        max-width: 450px;
        height: 100%;
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

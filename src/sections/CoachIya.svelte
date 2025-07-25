<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["coach-iya.jpg"];
    const captions = [
        `Coach Iya Karade pictured at the Athletic Arts Academy. <a href="https://www.wsj.com/articles/black-owned-businesses-hit-especially-hard-by-coronavirus-pandemic-study-finds-11596558754"> Source</a>`,
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
    <Scroller layout="left">
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
                <p>
                    An average of 12% of Black-owned businesses reported <a
                        href="https://www.brookings.edu/articles/who-is-driving-black-business-growth-insights-from-the-latest-data-on-black-owned-businesses/"
                        target="_blank"
                        rel="noopener noreferrer">an increase of sales,</a>
                    compared to only 5.5% of all businesses. Some were more able
                    to adapt and take advantage of the new economic environment while
                    others were hit hard.
                </p>
            </ObservedArticleText>

            <ObservedArticleText callback={setImageIndex(1)} {options}>
                <p>
                    In New Jersey, Coach IyaSokoya Karade had to shut down her
                    gymnastics studio, the Athletic Art Academy, when the
                    pandemic hit. She had to conduct virtual classes. When it
                    reopened in July 2021, it was operating only at 25% capacity
                    as many families continued staying at home in
                    multi-generational households, afraid of putting older
                    relatives at risk.
                </p>
                <br />
                <p>
                    “The word pivot became synonymous with survival,” said
                    Karade, 54, who started her business in 2014 to create the
                    youth fitness center for opportunities for gymnastics and
                    enjoyment for families in her urban area.
                </p>
                <br />
                <p>
                    She stated that whether she could continue to survive under
                    these conditions depends on various factors, such as
                    receiving more funding. About 37% of Black small-business
                    owners said they <a
                        href="https://www.cnbc.com/2021/02/18/black-small-business-owners-are-being-left-behind-amid-covid-pandemic.html"
                        target="_blank"
                        rel="noopener noreferrer">could survive more than a year under the</a>
                    conditions of the pandemic, compared to 59% of White
                    small-business owners and 55% Hispanic small-business
                    owners.
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

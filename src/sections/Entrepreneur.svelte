<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["everett-sands.jpg"];
    const captions = [
        `Source: <a href="https://inglewoodtoday.com/featured/celebrating-financial-literacy-month-lendistry-ceo-everett-sands-pioneers-with-scientific-brilliance/">Economic Policy Institute</a`,
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

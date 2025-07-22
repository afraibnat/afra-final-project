<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let imageIndex = 0;

    const images = ["business-operations.png"];
    const captions = [
        `Source: <a href="https://www.brookings.edu/articles/new-data-shows-small-businesses-in-communities-of-color-had-unequal-access-to-federal-covid-19-relief/">Brookings</a>`
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
                <h2>Recovery</h2>
                <p>Recently in February 2023, these rates remain high, conveying recovery.</p>

                <p>As you can see, the industries that were struggling during the pandemic 
                    and were highly-concentrated in black businesses are now flourishing (Accommodations, Food Service, Construction, Professional, and Health Services).</p>
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

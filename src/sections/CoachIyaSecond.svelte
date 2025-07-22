<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="page-wrapper">
    <div class="background-color" aria-hidden="true"></div>
    <Scroller layout="center">
        {#snippet sticky()}{/snippet}

        {#snippet scrolly()}
            <div class="text-box">
                <ArticleText>
                    At the same time, there was resilience among Black
                    small-business owners. Karade had said, “For most of us,
                    this is our opportunity to change things, not just for
                    ourselves but for the generations to come.”
                </ArticleText>

                <ArticleText>
                    Fast forward to 2024, Karade has been <a
                        href="https://www.handsinc.org/blog/celebrating-iyasokoya-karade-aka-coach-iya-of-a-hrefhttpswwwathleticartsacademynjcomathletic-arts-academya"
                        target="_blank"
                        rel="noopener noreferrer"
                        >fully equipped with a 10,500 sq. ft. youth fitness
                        center</a
                    > for children to compete beginner to competitive level gymnastics.
                </ArticleText>

                <ArticleText>
                    She recieved the HANDS grant back in 2022 to support her
                    business, and an additional award in 2024 for its impact on
                    the community.
                </ArticleText>
            </div>
        {/snippet}
    </Scroller>
</div>

<style>
    .background-color {
        position: absolute;
        inset: 0;
        background: #ffcc00;
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

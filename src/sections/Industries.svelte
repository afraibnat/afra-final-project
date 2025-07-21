<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObserverArticleSecond from "../lib/ObserverArticleSecond.svelte";
    import StickyBackground from "../lib/StickyBackground.svelte";

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<Scroller layout="center">
    {#snippet sticky()}
        <h2>Industries Most Hit</h2>
        <p>These are industries with some of the highest concentrations of African-American-owned businesses.</p>
    {/snippet}

    {#snippet scrolly()}
        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p>Accommodations, specifically Hotel and Leisure: Down by 35%</p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p>Food service (Restaurants): Down by 22%</p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p>Construction: Down by 27%</p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p>Professional and Business Services: Down by 18%</p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p>Health Services: Down by 16%</p>
        </ObserverArticleSecond>
    {/snippet}
</Scroller>

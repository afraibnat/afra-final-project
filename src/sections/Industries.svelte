<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObserverArticleSecond from "../lib/ObserverArticleSecond.svelte";

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
        <p>These are industries with some of the <a href="https://www.africanamericanchambersa.org/the-impact-of-covid-19-on-african-american-owned-businesses/" target="_blank" rel="noopener noreferrer">highest concentrations of African-American-owned businesses.</a></p>
    {/snippet}

    {#snippet scrolly()}
        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p><strong>Accommodations,</strong> specifically <strong>Hotel</strong> and <strong>Leisure:</strong> Down by <strong>35%</strong></p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p><strong>Food service (Restaurants):</strong> Down by <strong>22%</strong></p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p><strong>Construction:</strong> Down by <strong>27%</strong></p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p><strong>Professional</strong> and <strong>Business Services:</strong> Down by <strong>18%</strong></p>
        </ObserverArticleSecond>

        <ObserverArticleSecond callback={simpleCallback} {options}>
            <p><strong>Health Services:</strong> Down by <strong>16%</strong></p>
        </ObserverArticleSecond>
    {/snippet}
</Scroller>

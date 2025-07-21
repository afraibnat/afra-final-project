<script>
    // `layout` can be either "right" or "left"
    // `sticky` and `scrolly` are the snippets passed in (see one of the examples)
    let { layout, sticky, scrolly } = $props();
</script>

<div class="wrapper {layout}">
    <div class="sticky">
        {@render sticky()}
    </div>

    <div class="scrolly">
        {@render scrolly()}
    </div>
</div>

<style>
    .wrapper {
        background-color: #ffffff;
        padding: min(100vh, 30rem) 1rem;
        border-style: solid;
        border-color: #4096fa;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: flex-start;
    }

    .wrapper.center {
        flex-direction: column;
        align-items: center;
    }

    .left .scrolly {
        order: 0;
    }
    .left .sticky {
        order: 1;
    }

    .right .scrolly {
        order: 1;
    }
    .right .sticky {
        order: 0;
    }

    .center .sticky {
        order: 0;
        width: 100%;
        align-items: center;
        justify-content: center;
    }

    .center .scrolly {
        order: 1;
        width: 100%;
    }

    .sticky,
    .scrolly {
        display: flex;
        flex-direction: column;
        flex: 1 1; /* Allows growing, shrinking */
    }

    .sticky {
        position: sticky;
        top: 50vh;
        transform: translateY(-50%);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 2; 
        /* 0 */
    }

    .sticky-content {
        text-align: center;
        background-color: rgba(199, 127, 127, 0.6); /* transparent background */
        padding: 2rem;
    }

    .scrolly {
        z-index: 1;
    }

    @media (max-width: 768px) {
        .wrapper {
            flex-direction: column;
            padding: 2rem 1rem;
            width: 100vw;
        }

        .sticky,
        .scrolly {
            flex: 1 1 auto;
            min-width: 100%;
            position: static; /* remove sticky on mobile */
            transform: none;
        }

        .sticky {
            margin-bottom: 2rem;
        }
    }
</style>

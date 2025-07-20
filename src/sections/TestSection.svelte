<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText2 from "../lib/ArticleText.svelte";
</script>

<Scroller layout="left">
    {#snippet sticky()}
        <h1>hello</h1>
    {/snippet}

    {#snippet scrolly()}
    <ArticleText2>
        <p><strong>
            With the economic fallout during the COVID-19 pandemic in 2020, 
            the most deeply impacted racial group were Black-owned businesses, 
            seeing a 41% decline in number, along with the collapse of 440,000. 
            Furthermore, Black Americans faced an unemployment rate of 16.8%.
        </strong></p>
        <p>
            But this collapse was a result of long-term civil and economic justices. 
            Black people were not allowed in white restaurants, universities, churches, 
            or businesses due to Jim Crow laws and segregation, barriers meant to keep 
            Black people from having the same opportunities from white people, 
            leading to many starting their own to rely on self-sufficiency. 
        </p>
        <p>
            As a result, there came the “Golden Age” of Black-owned businesses from 1900 to 1930. 
            The number of Black-owned companies doubled from 20,000 to 40,000 between 1900 and 1915, 
            according to the National Negro Business League. 
        </p>
        <p>
            Independent black-owned businesses played a significant role in financing civil rights protests 
            during the 1950s and 60s. Grocery store owner Daniel Speed bankrolled a bus boycott 
            similar to the Montgomery boycott, and his shop served as a meeting ground for black leaders. 
        </p>
</ArticleText2>

    {/snippet}
</Scroller>
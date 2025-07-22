<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="page-wrapper">
  <div class="background-color" aria-hidden="true"></div>
  <Scroller layout="center">
    {#snippet sticky()}{/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <div class="text-box">
          <h2>Who are Black Business Owners?</h2>
          <p>
            <strong>More Likely to be Men than Women.</strong> Some 54% of Black-owned
            firms in 2022 had men as their majority owners, while 39% had women as
            their majority owners.
          </p>
          <p>
            <strong>A Greater Percentage are Middle-Aged.</strong> Half of Black
            or African American business owners who reported their age group were
            ages 35 to 54 in 2022.
          </p>
          <p>
            <strong>A Majority have a College Degree.</strong> Among owners who reported
            their highest level of education completed, 27% had a bachelor’s degree
            and 34% had a graduate or professional degree beyond a bachelor’s in
            2022.
          </p>
        </div>
        <div class="chart-footnote">
          Source:
          <a
            href="https://www.pewresearch.org/short-reads/2025/02/12/a-look-at-black-owned-businesses-in-the-us/"
          >
            Pew Research Center
          </a>
        </div>
      </ArticleText>
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

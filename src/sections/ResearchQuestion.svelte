<script>
  import FullPageText from "../lib/FullPageText.svelte";
  import { slide } from 'svelte/transition';
  import { onMount } from 'svelte';

  let show = false;
  const subtitle = "How has Black business ownership varied across U.S. metropolitan areas over the past decades, and what role did the COVID-19 pandemic play in accelerating or reversing these trends?";

  onMount(() => {
    show = true;
  });
</script>

{#if show}
    <div transition:slide={{ duration: 500, delay: 100 }}>
        <FullPageText {subtitle}/>
    </div>
{/if}
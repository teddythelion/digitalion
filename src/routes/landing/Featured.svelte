<script lang="ts">
  import Dev from '../utils/icons/Dev.svelte';
  import GitHub from '../utils/icons/GitHub.svelte';
  import YouTubeFull from '../utils/icons/YouTubeFull.svelte';
  import Discord from '../utils/icons/Discord.svelte';
  import Figma from '../utils/icons/Figma.svelte';
  import Community from '../utils/icons/Community.svelte';
  import Reddit from '../utils/icons/Reddit.svelte';
  import Combinator from '../utils/icons/Combinator.svelte';

  const features = {
    'https://github.com/teddythelion/teddythelion/blob/main/README.md': GitHub,
    'https://www.facebook.com/digitalionedia/': Dev,    
    'https://www.facebook.com/digitalionmeda/': YouTubeFull,
    'https://www.facebook.com/digitalionmedi/': Discord,
    'https://www.facebook.com/digitalioned/': Figma,    
    'https://www.linkedin.com/in/teddy-deleon-': Community,
    'https://www.linkedin.com/in/teddy-deleon-2408126b': Reddit,
    'https://www.linkedin.com/in/teddy-deleon-4908126b': Combinator,    
    'https://www.facebook.com/digitalionmedia/': YouTubeFull
  };
</script>

<div class="py-6 px-4 lg:px-20">
  <div class="flex flex-col px-4 gap-2">
    <div class="mx-auto text-base tracking-tight lg:hidden mb-4">Check out:</div>
    <div class="flex flex-wrap items-center gap-8 justify-center lg:hidden">
      {#each Object.entries(features) as [href, comp]}
        <a href = {href}><svelte:component this={comp}/></a>
      {/each}
    </div>
    <div class="items-center gap-8 justify-center self-stretch py-2 hidden lg:flex flex-wrap">
      <div class="text-base tracking-tight">Check out:</div>
      {#each Object.entries(features) as [href, comp]}
        <a href = {href}><svelte:component this={comp} /></a>
      {/each}
    </div>
  </div>
</div>

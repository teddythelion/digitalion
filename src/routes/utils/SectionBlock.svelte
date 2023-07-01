<script lang="ts">
  import { page } from '$app/stores';
  import { Section } from '$lib';
  import EditOnGithub from './EditOnGithub.svelte';
  import  DocsLink  from './DocsLink.svelte';
  export let title: string = '';
  const href = `https://github.com/teddythelion`;
</script>

<Section name="none" classSection="py-6 sm:py-10 text-center" classDiv="px-4 mx-auto max-w-8xl text-center">
  <div class="grid lg:grid-cols-2 justify-center">
    <div>
      <h2 class="mb-1 text-2xl font-semibold text-center tracking-tight text-gray-900 dark:text-white">
        {title}
      </h2>
      <p class="text-lg text-gray-500 lg:mb-0 dark:text-gray-400 lg:max-w-2xl">
        <slot />
      </p>
    </div>
    <div class="flex items-center lg:justify-end mt-2 lg:mt-0">
      <EditOnGithub size="16" {href} iconClass="text-gray-500" target="_blank" />
      <DocsLink page={title.toLowerCase().replace(/\s+/g, '-')} target="_blank" />
    </div>
  </div>
</Section>

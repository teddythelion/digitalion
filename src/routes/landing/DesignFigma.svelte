<script>
  import Button from '$lib/buttons/Button.svelte';
  import ArrowRight from '../utils/icons/ArrowRight.svelte';

</script>

<div class="flex flex-col items-center px-4 py-8 lg:px-20 lg:py-24 gap-2.5 bg-gray-50 dark:bg-gray-800">
  <div class="flex flex-row items-start justify-between gap-24 py-1">
    <div class="flex flex-col gap-8">
      <div class="flex flex-col items-start gap-6">
        <h3 class="leading-none text-3xl lg:text-4xl font-extrabold text-gray-900 dark:text-white">
          Elegant Designs
        </h3>
        <p class="text-lg">
          Digital Lion Media creates designs that are not only functional and elegant but that are engineered with SEO and digital marketing from the first line of code. We have ways of using syntax in the code that act as key-word maps for specicic pages for example tags classes and ID's are key word specific for the page implimented in. This helps Google determine the purpose and targets of each page. We have an every page as a landin page mindset.
        </p>
      </div>
      <div class="flex flex-col items-center gap-4">
        
        <div class="flex flex-col items-start gap-4 isolate self-stretch max-w-l">
          <Button color="light" class="self-stretch !px-4 !justify-start gap-5 sm:gap-7" size="xl" href='https://classtactics.com/'
            > See Design Layout
            <div class="ml-auto hidden sm:block"><ArrowRight /></div></Button>
          <Button color="light" class="self-stretch !px-4 !justify-start gap-4 sm:gap-6" size="xl" href='https://ai-codelabs.com'
            > Click-drag on images
            <div class="ml-auto hidden sm:block"><ArrowRight /></div></Button>
        </div>
      </div>
    </div>
    <div class="flex-col items-start hidden lg:flex">
      <div class="relative dark:hidden rounded-xl">
        <img class="max-w-2xl" src="/images/figma.png" alt="Header" />
      </div>
      <div class="hidden relative dark:block">
        <img class="max-w-2xl rounded-xl" src="/images/figma-dark.png" alt="Header" />
      </div>
    </div>
  </div>
</div>

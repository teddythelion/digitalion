<script lang="ts">
  import { page } from '$app/stores';
  import Footer from '../../lib/footer/Footer.svelte';
  import FooterBrand from '../../lib/footer/FooterBrand.svelte';
  import FooterCopyright from '../../lib/footer/FooterCopyright.svelte';
  import FooterIcon from '../../lib/footer/FooterIcon.svelte';
  import FooterLink from '../../lib/footer/FooterLink.svelte';
  import FooterLinkGroup from '../../lib/footer/FooterLinkGroup.svelte';
  let logo = '/images/digitalionmedia.svg';

  let isHomePage: boolean;
  $: isHomePage = $page.route.id === '/';

  const footer_links = {
    Resources: {
      GitHub: "https://github.com/teddythelion/",
      Facebook: "https://www.facebook.com/digitalionmedia/",
      'dlm': "https://digitalionmedia.com",
      'dlma': 'https://www.facebook.com/digitalionmedia//'
    },
    'Help and Support': {
      'AI Codelabs': "https://ai-codelabs.com",
      'GitHub Discussions': "https://github.com/teddythelion/teddythelion/blob/main/README.md"
    },
    Legal: {
      License: "https://github.com/teddythelion/teddythelion/blob/main/README.md",
      'Brand usage': "https://github.com/teddythelion/teddythelion/blob/main/README.md"
    }
  };
</script>

<Footer footerType="custom" customClass="bg-white dark:bg-gray-800">
  <div class="flex flex-col py-6 lg:py-12">
    <div class="flex flex-col lg:flex-row items-start md:justify-between gap-8 {isHomePage ? 'px-4 lg:px-20' : ''}">
      <div class="mb-6 md:mb-0 w-full max-w-sm">
        <FooterBrand
          href="https://digitalionmedia.com"
          src={logo}
          alt="dlm Logo"
          name="DLM"
          class="text-gray-900 dark:text-white" />
        <p class="max-w-sm mb-3 text-gray-600 dark:text-gray-400 mt-4">
          Digitalionmedia.com is the website of Digital Lion Media. We are a media company that uses data and AI to better understand individual business models by applying the power of AI.
        </p>
        <p class="max-w-sm mb-3 text-gray-600 dark:text-gray-400">
        Digital Lion Media, LLC
          <a
            href="https://digitalionMedia.com"
            class="text-primary-600 hover:underline">
            IE
          </a>Riverside
          <a href="https://creativecommons.org/licenses/by/3.0/" class="text-primary-600 hover:underline"
            >2023</a
          >.
        </p>
      </div>
      <div class="flex flex-col md:flex-row items-start {isHomePage ? 'gap-16 lg:justify-end' : 'gap-8'}  w-full">
        {#each Object.entries(footer_links) as [column, links]}
          <div>
            <h2 class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white">{column}</h2>
            <FooterLinkGroup>
              {#each Object.entries(links) as [name, href]}
                <FooterLink liClass="mb-4" {href}>{name}</FooterLink>
              {/each}
            </FooterLinkGroup>
          </div>
        {/each}
      </div>
    </div>
    <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
    <div class="sm:flex sm:items-center sm:justify-center">
      <FooterCopyright
        href="/"
        by="DLM™"
        copyrightMessage="All Rights Reserved." />
    </div>
  </div>
</Footer>

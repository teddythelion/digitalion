<script lang="ts">

import { MetaTags } from 'svelte-meta-tags';
//import type { PageData } from './$types';

import Featured from './landing/Featured.svelte';
import Hero from './landing/Hero.svelte';
import Footer from './utils/Footer.svelte';

import DesignFigma from './landing/DesignFigma.svelte';
import GetStarted from './landing/GetStarted.svelte';
import ContentFeature from './landing/contentFeature.svelte';
import Contact from './landing/contact.svelte';
let title = 'Digital Lion Media - ';
  let description =
    'Digital Lion Media is Wdb and data company utilizing AI for leverageing big data';
  let default_title = 'Digital Lion Media LLC';
  const image = `https://open-graph-vercel.vercel.app/api/flowbite-svelte?title=${default_title}`;
</script>

  
  <MetaTags
    {title}
    {description}
    facebook={{ appId: '453670756870545' }}
    openGraph={{
      type: 'website',
      url: `https://digitalionmedia.com`,
      title: `${title}`,
      description: `${description}`,
      images: [{ url: image, width: 1200, height: 630, alt: `${title}` }],
      site_name: 'Digital Lion Media'
    }}
    twitter={{
      handle: '@teddythlion',
      cardType: 'summary_large_image',
      title: `${title}`,
      description: `${description}`,
      image,
      imageAlt: `${title} logo`
    }} />
  
  <main
    class="flex-auto dark:bg-grey-800 mx-auto max-w-8xl min-w-0 lg:static lg:max-h-full lg:overflow-visible divide-y dark:divide-gray-700">
    <Hero />
    <Featured />
    <ContentFeature/>
    <DesignFigma /> 
    <Contact />
    <Footer />
  </main>
  
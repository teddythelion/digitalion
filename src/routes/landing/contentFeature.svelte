<script>
    import {
      Section,
      HeroHeader,
      FeatureDefault,
      FeatureItem      
    } from '$lib';
    
   
    import {  
      PresentationChartLine,
      AcademicCap,
      Cog,
      Briefcase,
      CurrencyDollar,
      Bolt,
      ChevronRight
    } from 'svelte-heros';
   
  </script>
<Section class = "dark: bg-gray-800" name="feature">
    <HeroHeader
      class="max-w-screen-md mb-8 lg:mb-16"
      h2Class="mb-4 text-4xl tracking-tight font-extrabold text-gray-900 dark:text-white"
      pClass="text-gray-500 sm:text-xl dark:text-gray-400"
    >
      <svelte:fragment slot="h2">What we actually do</svelte:fragment>
      <svelte:fragment slot="paragraph"
        >Digital Lion Media is all about the growth mindet as cliche as that sounds. If we are not growing and improving then we are not content. That is why we strive to be and become the best at whatever we do.</svelte:fragment
      >
    </HeroHeader>
    <FeatureDefault>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><PresentationChartLine
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Marketing-SEO</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >The first thing that is done is AI assisted data aggregation. From the data and feedback you give a Website is built using very targeted keyword mapping.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><AcademicCap
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Metrics</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Using different metrics tools your site when built or revamped will be graded on several different metrics such as page speed, readabilty and keyword variabilty.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><Briefcase
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Social Media</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >This may be the most important step these days. I will set up each profile to create brand consistancy acorss all social media properties and craft a brand awareness campaign.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><CurrencyDollar
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Content Creation</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >We are going to create amaxing content that give tremendous value to your potential customer. Content marketing is a solid way to build loyal customers because you give away hard learned experience in the content.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><Bolt
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Integration</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Taking all the data and social media and website content and creating a coherent message that inspires and looks amazing will drive engagement with your brand in so many ways.</svelte:fragment
        >
      </FeatureItem>
      <FeatureItem>
        <svelte:fragment slot="icon"
          ><Cog
            class="w-5 h-5 text-primary-600 lg:w-6 lg:h-6 dark:text-primary-300"
          /></svelte:fragment
        >
        <svelte:fragment slot="h3">Automation</svelte:fragment>
        <svelte:fragment slot="paragraph"
          >Once everything is set up and we have optimized everything to perfection(as close as we can) we create automated workflows and AI handle the busy work on auto pilot. Thing will be getting done all hours of th day..</svelte:fragment
        >
      </FeatureItem>
    </FeatureDefault>
  </Section>
<script lang="ts">
  import { MetaTags } from 'svelte-meta-tags';
  export let withoutLink: boolean = false;
  export let breadcrumb_title: string = '';
  export let description: string = '';
  export let title: string = '';
  // title = title.replaceAll(' ', '-');
  let imgsrc ="/static/images/digitalionmedia.svg";
  
  let url: string = 'https://digitalionmedia.com/';
  export let dir: string = '';
  let breadcrumb = breadcrumb_title.toLowerCase().replaceAll(' ', '-');
  let urlLink = withoutLink ? '' : breadcrumb;
  if (dir) {
    let dirstring = dir.toLowerCase() + '/';
    url = `https://digitalionmedia.com/`;
  }
</script>

<MetaTags
  title={breadcrumb_title}
  titleTemplate="%dlm"
  {description}
  facebook={{
    appId: '672622757749720'
  }}
  openGraph={{
    type: 'website',
    url: `${url}`,
    title: `DLM${title}`,
    description: `${description}`,
    images: [
      {
        url: imgsrc,
        width: 1200,
        height: 630,
        alt: `${title}`
      }
    ],
    site_name: 'Digital Lion Media LLC'
  }}
  twitter={{
    handle: '@teddythelion',
    cardType: 'summary_large_image',
    title: `teddyDeleon`,
    description: `${description}`,
    image: imgsrc,
    imageAlt: `${title}`
  }}
/>

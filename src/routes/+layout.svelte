<script lang="ts">
  import { page } from '$app/stores';
  import  Navbar from '../lib/navbar/Navbar.svelte';
  import  NavBrand from '../lib/navbar/NavBrand.svelte';
  import  NavUl from '../lib/navbar/NavUl.svelte';
  import  NavLi from '../lib/navbar/NavLi.svelte';
  import  NavHamburger from '../lib/navbar/NavHamburger.svelte';
  import Tooltip from '../lib/tooltips/Tooltip.svelte';
  import DarkMode from '../lib/darkmode/DarkMode.svelte';
  import { setContext } from 'svelte';
  import { writable, type Writable } from 'svelte/store';
  import '../app.css';
  import DocBadge from './utils/DocBadge.svelte';
 // import ToolbarLink from './ToolbarLink.svelte';
  import type { LayoutData } from './$types';
  import NavSidebarHamburger from '$lib/navbar/NavSidebarHamburger.svelte';

 let data: LayoutData;

  let isHomePage: boolean;
  $: isHomePage = $page.route.id === '/';



  $: activeUrl = $page.url.pathname;
  let logo = '/images/digitalionmedia.svg';
  let divClass = 'w-full ml-auto lg:block lg:w-auto order-1 lg:order-none';
  let ulClass =
    'flex flex-col py-3 my-4 lg:flex-row lg:my-0 text-sm font-medium text-gray-900 dark:text-gray-300 gap-4';

  const drawerHiddenStore: Writable<boolean> = writable<boolean>(true);
  setContext('drawer', drawerHiddenStore);

  const toggleDrawer = () => {
    drawerHiddenStore.update((state) => !state);
  };
</script>

<header
  class="sticky top-0 z-40 flex-none w-full mx-auto bg-white border-b border-gray-200 dark:border-gray-600 dark:bg-gray-800">
  <Navbar
    color="default"
    fluid
    navClass="flex items-center justify-between w-full mx-auto py-1.5 px-4 {isHomePage
      ? 'max-w-8xl lg:px-20 px-4'
      : ''}"
    let:hidden
    let:toggle>
    <span hidden={$page.route.id === '/'}>
      <NavSidebarHamburger on:click={toggleDrawer} btnClass="mr-3 m-0 mr-3 lg:hidden" />
    </span>
    <NavBrand href="/">
      <img src={logo} class="mr-3 h-14" alt="digital lion media logo" />
      <span class="self-center whitespace-nowrap text-2xl font-semibold text-gray-900 dark:text-white">
        Digital Lion Media LLC
      </span>
    </NavBrand>

    <NavUl
      {hidden}
      {divClass}
      {ulClass}
      on:click={() => setTimeout(toggle, 1)}
      nonActiveClass="md:!pl-3 md:!py-2 lg:!pl-0 text-gray-700 hover:bg-gray-100 lg:hover:bg-transparent lg:border-0 lg:hover:text-primary-700 dark:text-gray-400 lg:dark:text-white lg:dark:hover:text-primary-700 dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent"
      activeClass="md:!pl-3 md:!py-2 lg:!pl-0 text-white bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:dark:text-primary-700 dark:bg-primary-600 lg:dark:bg-transparent cursor-default">
      <NavLi class="lg:px-2 lg:mb-0" active={activeUrl === '/'} href="/">Home</NavLi>
    
    </NavUl>

    <div class="flex items-center ml-auto">
      
    
      <DarkMode size="lg" class="inline-block dark:hover:text-white hover:text-gray-900" />
      <Tooltip class="dark:bg-gray-900" placement="bottom-end">Toggle dark mode</Tooltip>
    </div>
   

    <NavHamburger on:click={toggle} btnClass="ml-3 m-0 lg:hidden {isHomePage ? '' : 'hidden'}" />
  </Navbar>
</header>

<div class="lg:flex dark:bg-grey-800">
  <slot />
</div>
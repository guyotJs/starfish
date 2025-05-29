<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import Header from './lib/Header.svelte';
  // import Sno from './lib/Sno.svelte';
  import Filler from './lib/Filler.svelte';
  import Links from './lib/Links.svelte';
  import Wotw from './lib/Wotw.svelte';
  import Fronds from './lib/body/Fronds.svelte';
  import Apps from './lib/body/Apps.svelte';
  import Settings from './lib/body/Settings.svelte';
  import Modal from './lib/body/Modal.svelte'
  import Versions from './lib/body/Versions.svelte';
  import {setCookie, getCookie} from "./cookies.js";

  let visable = $state(false);
  let version = $state("צ");
  let date = $state("05/28/2025")
  let dark = $state(false);
  let bgImg = $state("url(https://guyotjs.github.io/consoles/n64Light.png)");
  let toBlend = $state("rgba(255,255,255,0.8)");
  let blender = $state("lighten");
  let showModal = $state(false);

  function swapVisibility(){
    showModal = !showModal;
  }
  
  function swapMode(){
    if(!dark){
      setCookie("dark","true",365);
      dark = true;
      blender = "darken";
      bgImg = "url(https://guyotjs.github.io/consoles/n64Dark.png)";
      toBlend = "rgba(36,36,36,0.9)";
    }
    else{
      setCookie("dark","false",365);
      dark = false;
      blender = "lighten";
      bgImg = "url(https://guyotjs.github.io/consoles/n64Light.png)";
      toBlend = "rgba(255,255,255,0.8)";
    }
  }
  if(getCookie("dark") == "true"){
    swapMode();
  }
  onMount(async ()=>{
    visable = true;
  });
</script>
<style>
  .img{
    position:fixed;
    width:100%;
    height:100%;
    left:0;
    top:0;
    z-index: -100;
    background-image: var(--currentbg),
      radial-gradient(circle at 30% 30%, rgba(5, 255, 255, 0.5), transparent 100%),
      radial-gradient(circle at 70% 90%, rgba(255, 5, 255, 0.5), transparent 100%);;
    background-color: var(--color);
    background-blend-mode: var(--blender);
    background-repeat:no-repeat;background-size:cover;background-position:center center;background-attachment:fixed!important;
  }
</style>
<svelte:head>
  <title>Guyot {version}</title>
  <link rel="shortcut icon" href="https://guyotjs.github.io/duckclear2.png" type="image/x-icon">
</svelte:head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<div style="--currentbg: {bgImg};--color:{toBlend};--blender:{blender};" class="img"></div>
<Header {visable} {version} {dark}/>
  {#if visable}
    <div in:fade="{{delay: 1400 + 3 * 150, duration: 800}}">
      <!-- <div class="text-center italic" class:white={dark}>Revision 1</div> -->
      <!--
        Header Content
      -->
      <!-- <Sno {dark}/> -->
      <Links {dark}/>
      <Wotw {dark}/>
      <!--
        Bondy Content
      -->
      <Fronds {dark}/>
      <Apps {dark}/>  
      <Versions {dark}/>
      <Settings {dark} {swapMode} {version} {date} {swapVisibility}/>
      <Modal bind:showModal {dark}>
        <div style="float: right;">
          <img src="https://nueot-437a9.web.app/duckclear2.png" width="100px" alt="Guyot">
        </div>
        {#snippet header()}
          <h2>
            Guyot {version}
          </h2>
        {/snippet}
        The Guyot Project is an open source unblocked emulator<br/>
        The Guyot Project ©2025 is licensed with <u>MIT</u>.<br/>
        Guyot {version} includes GBA SNES, and N64 titles.<br/>
        All games are licensed by Nintendo.<br/>
      </Modal>
      
    </div>
  {/if}
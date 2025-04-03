<script>
  let { visable, version, dark } = $props();
  import { fade } from 'svelte/transition';
  let isAnimating = $state(false);

  function startAnimation() {
    isAnimating = true;
  }
  function resetAnimation() {
    isAnimating = false;
  }
</script>
<link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
<style>
  p,span{
    display: inline-block;
    font-family: serif!important;
  }
  .f-xxl{
    font-size: 50px;
  }
  .pt-xl{
    padding-top: 30px;
    padding-bottom: 15px;
  }
  .toHoverMachine{
    transition: 0.3s;
  }
  @keyframes spin{
    from{
      transform: rotate(0deg);
    }
    to{
      transform: rotate(360deg);
    }
  }
  .animation{
    animation: spin 1s ease-in-out;
  }
  .hoverish{
    transition: 0.3s;
  }
  .toHoverMachine:hover > #G{display: inline-block;transform: rotate(35deg)translate(-7px,5px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine:hover > #U{display: inline-block;transform: rotate(-5deg)translate(7px,15px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine:hover > #Y{display: inline-block;transform: rotate(-35deg)translate(10px,-12px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine:hover > #O{display: inline-block;transform: rotate(50deg)translate(12px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine:hover > #T{display: inline-block;transform: rotate(-35deg)translate(10px,-5px);transition: ease-in-out 0.3s;font-family: serif!important;}

  .toHoverMachine > #G{display: inline-block;transform: rotate(0deg)translate(0px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine > #U{display: inline-block;transform: rotate(0deg)translate(0px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine > #Y{display: inline-block;transform: rotate(0deg)translate(0px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine > #O{display: inline-block;transform: rotate(0deg)translate(0px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
  .toHoverMachine > #T{display: inline-block;transform: rotate(0deg)translate(0px,0px);transition: ease-in-out 0.3s;font-family: serif!important;}
</style>
<div class="text-center f-xxl pt-xl" style="user-select:none;">
  <span class="toHoverMachine">
    {#each "GUYOT" as letter,i}
      {#if visable}
      <p in:fade="{{delay: 500 + i * 150, duration: 800}}" id={letter} class:white={dark}>{letter}</p>
      {/if}
    {/each}
  </span>
  <br/>
  {#each version as letter,i}
    {#if visable}
      <p in:fade="{{delay: 1000 + i * 150, duration: 800}}" class:animation={isAnimating} onmouseenter={startAnimation} onanimationend={resetAnimation} class="hoverish" class:white={dark}>{letter}</p>
    {/if}
  {/each}
</div>
<script>
  let {dark,swapMode,version,date,swapVisibility} = $props();
  let visable = $state(false);
  function toggle(){
    visable = !visable;
  }
</script>
<style>
  .w-react{
    display:grid;
    width:min(500px,90%);
    margin-left:50%;
    transform: translate(-50%);
  }
  .hover:hover{font-weight: 900;}
</style>
<link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<div class="text-center p w-react m-m blur" class:white-border={dark} class:dark={!dark}>
  <div style="display:inline-block">
    <button class="fake-button f hover-bold" class:white={dark} onclick={toggle}> <i class="fa fa-envelope-o"></i> Extras </button>
  </div>
  <hr/>
  {#if visable}
    <div class="text-center">
      {#if !dark}
        <span>Dark mode </span>
        <button class:nin={!dark}  onclick={swapMode}>
          <i class="fa fa-moon-o"></i>
          <span style="display:none;">a</span>
        </button>
      {:else}
        <span class="white">Light mode </span>
        <button class:nin={!dark} onclick={swapMode}>
          <i class="fa fa-sun-o white"></i>
          <span style="display:none;">a</span>
        </button>
      {/if}<br/>
      <p class:white={dark}>
        Release <b class:white={dark} class="true-serif">{version}</b> Rev1, <em class:white={dark}>{date}</em><br/>
        Made by, <span class:white={dark} class="hover">Weston</span><br/>
        <button class:white={dark} onclick={swapVisibility} class:nin={!dark}>Legal + Info</button> 
        
      </p>
    </div>
  {/if}
</div>

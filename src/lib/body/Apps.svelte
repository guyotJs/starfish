<script>
  let {dark} = $props();
  let selected = $state(undefined);
  let apps = $state([
    ["Books","https://guyotjs.github.io/books"],
    ["Credits","https://guyotjs.github.io/credits"],
    ["Time","https://guyotjs.github.io/tm",true],
    ["Tusky Time","https://tuskytime.org"],
    ["Weston","https://classicmc-studios.github.io/Westonism/snowstorm/"],
    ["Boyce VA","https://guyotjs.github.io/boyce/",true],
    ["Sno","https://snojs.github.io"],
    ["Polycarp","https://guyotjs.github.io/Polycarp"],
    ["Bible","https://classicmc-studios.github.io/bible/",true]
  ])
</script>
<link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
  .w-react{
    display:grid;
    width:min(500px,90%);
    margin-left:50%;
    transform: translate(-50%);
  }
  .blur{
    backdrop-filter:blur(5px);
    -webkit-backdrop-filter: blur(5px);
  }
  .white{
    border:1px solid gray;
    border-radius: 5px;
  }
  .dark{
    border: 1px solid lightgray;
    border-radius: 5px;
  }
  .nue-calm{
    color:#49d0a7;
  }
  hr{
    border-color: rgba(0,0,0,0);
    margin:1px;
  }
  a:hover{
    font-weight: 900;
    /* text-decoration: line-through; */
  }
  a{
    margin: 3px;
  }
</style>
<div class="text-center p w-react m-m blur" class:white={dark} class:dark={!dark}>
  <div style="display:inline-block">
    <i class="fa fa-laptop"></i> Sites
  </div>
  <hr/>
  <div class="text-center">
    {#each apps as app,i}
      {#if app[2]}
        <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
        {:else}
        <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&emsp;
      {/if}
    {/each}
  </div>
</div>

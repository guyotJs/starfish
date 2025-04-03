<script>
  let {dark} = $props();
  let selected = $state("NONE");

  function selectGBA(){selected = "GBA";}
  function reset(){selected = "NONE";}
  function selectSNES(){selected = "SNES";}
  function selectN64(){selected = "N64";}
  function selectOLD64(){selected = "OLD";}
  function selectFLASH(){selected = "FLASH";}

  let gba = $state([
    ["Doom","./games/doom.html"],
    ["FF 1&2 Advance","https://nueot-437a9.web.app/games/ff12.html"],
    ["FFV Advance","https://nueot-437a9.web.app/games/ffv.html",true],
    ["Leafgreen","https://nueot-437a9.web.app/games/lg.html"],
    ["FFIV Advance","https://nueot-437a9.web.app/games/ffivadv.html"],
    ["Mario Kart Super Circut","https://nueot-437a9.web.app/games/mksc.html",true],
    ["Emerald","https://nueot-437a9.web.app/games/emerald.html"],
    ["Minish Cap","https://nueot-437a9.web.app/games/mc.html"],
    ["Spyro","https://nueot-437a9.web.app/games/spyro.html",true],
    ["FFVI Adv","https://nueot-437a9.web.app/games/ffvien.html"],
    ["Kirby Nightmare","https://nueot-437a9.web.app/games/nightmare.html"]
  ]);
  let snes = $state([
    ["FFIV","https://nueot-437a9.web.app/games/ffiv-snes.html"],
    ["FFVI (3)","https://nueot-437a9.web.app/games/ffvi-snes.html"],
    ["Link to the Past","https://nueot-437a9.web.app/games/lttp.html",true],
    ["Super Mario Kart","https://nueot-437a9.web.app/games/smk.html"],
    ["Yoshi's Island","https://nueot-437a9.web.app/games/yo.html"],
    ["Yoshi's Island ROM Hack","https://nueot-437a9.web.app/games/yoshi.html",true],
    ["Mario World","https://nueot-437a9.web.app/games/smw.html"],
    ["Earthbound","https://nueot-437a9.web.app/games/eb.html"],
    ["Street Fighter 2","https://nueot-437a9.web.app/games/sf2t.html",true],
    ["Donkey Kong Country","https://nueot-437a9.web.app/games/dkc.html"],
    ["Super Meteroid","https://nueot-437a9.web.app/games/sm.html"],
    ["F-Zero","https://nueot-437a9.web.app/games/f0.html",true],
    ["Star Fox","https://nueot-437a9.web.app/games/sf.html"],
    ["Kirby Superstar","https://nueot-437a9.web.app/games/superkirby.html"],
    ["Pilotwings","https://nueot-437a9.web.app/games/pilot.html",true],
    ["Secret of Mana","https://nueot-437a9.web.app/games/secretom.html"],
    ["Super Ghouls and Ghosts","https://nueot-437a9.web.app/games/ghouls.html"],
    ["Megaman X","https://nueot-437a9.web.app/games/megamanx.html",true],
    ["Contra 3","https://nueot-437a9.web.app/games/contra3.html"],
    ["Kirby Dreamland","https://nueot-437a9.web.app/games/dreamland.html"],
    ["Super Mario RPG","https://nueot-437a9.web.app/games/mariorpg.html",true],
    ["Terranigma","https://nueot-437a9.web.app/games/terranigma.html"],
    ["Super Mario World","https://nueot-437a9.web.app/games/smw.html"],
  ])
  let n64 = $state([
    ["Mario Kart 64","https://nueot-437a9.web.app/games/mk64.html"],
    ["Super Smash Bros 64","https://nueot-437a9.web.app/games/ssb.html"],
    ["Paper Mario","https://nueot-437a9.web.app/games/pm.html",true],
    ["Super Mario 64","https://nueot-437a9.web.app/games/sm64.html"],
    ["Mario Tennis 64","https://nueot-437a9.web.app/games/mt.html"],
    ["Star Fox 64","https://nueot-437a9.web.app/games/sf64.html",true],
    ["Donkey Kong 64","https://nueot-437a9.web.app/games/dk64.html"],
    ["Harvest Moon 64","https://nueot-437a9.web.app/games/hm64.html"],
    ["Ocarina of Time","https://nueot-437a9.web.app/games/tlozoc.html",true],
    ["Banjo Kazooie","https://nueot-437a9.web.app/games/bk64.html"],
    ["Quake 64","https://nueot-437a9.web.app/games/quake64.html"],
    ["Kirby 64","https://nueot-437a9.web.app/games/kirby64.html"],
  ])
  let old = $state([
    ["Ocarina of Time","http://classicmc-studios.github.io/NeptunJS/tlozoc.html"],
    ["Mario Tennis","http://classicmc-studios.github.io/NeptunJS/mt.html"],
    ["Mario Kart 64","http://classicmc-studios.github.io/NeptunJS/mk64.html"]
  ])
  let flash = $state([
    ["Riddle School 1","https://guyotjs.github.io/flash/games/rs1.html"],
    ["Riddle School 2","https://guyotjs.github.io/flash/games/rs1.html",true],
    ["Riddle School 3","https://guyotjs.github.io/flash/games/rs3.html"],
    ["Fancy Pants Adventure","https://guyotjs.github.io/flash/games/fpa.html",true],
    ["Breaking the Bank","https://guyotjs.github.io/flash/games/btb.html"],
    ["Escaping the Prison","https://guyotjs.github.io/flash/games/etp.html",true],
    ["Stealing the Diamond","https://guyotjs.github.io/flash/games/std.html"],
    ["Bloxors","https://guyotjs.github.io/flash/games/b.html",true],
    ["Duck Life Treasure Hunt","https://guyotjs.github.io/flash/games/dlth.html"],
    ["Fleeing the Complex","https://guyotjs.github.io/flash/games/ftc.html",true],
    ["I'm Outta Here","https://guyotjs.github.io/flash/games/ioh.html"],
    ["Infiltrating the Airship","https://guyotjs.github.io/flash/games/ita.html",true],
    ["Line Rider","https://guyotjs.github.io/flash/games/lr2.html"],
    ["Super Mario Flash 2","https://guyotjs.github.io/flash/games/smf2.html",true],
    ["Super Smash Flash","https://guyotjs.github.io/flash/games/ssf.html"],
    ["The Binding of Issac","https://guyotjs.github.io/flash/games/tboi.html",true],
    ["The World's Hardest Game","https://guyotjs.github.io/flash/games/twhg.html"],
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
  .small{
    font-size: 12px;
  }
  .nue-calm{
    color:#49d0a7;
  }
  .no-m{
    margin:0;
  }
  .blur{
    backdrop-filter:blur(5px);
    -webkit-backdrop-filter: blur(5px);
  }
  a{
    margin: 3px;
  }
  .white-border{
    border:1px solid gray;
    border-radius: 5px;
  }
  .dark{
    border: 1px solid lightgray;
    border-radius: 5px;
  }
  button:not(.fake-button){
    background-color: rgba(0,0,0,0);
    border: 1px solid rgba(0,0,0,0);
    border-radius: 3px;
    padding:2px;
  }
  button:hover:not(.fake-button){
    border: 1px solid lightgray;
  }
  .fake-button{
    background-color: rgba(0,0,0,0);
    border: none;
  }
  hr{
    border-color: rgba(0,0,0,0);
    margin:1px;
  }
  a:hover{
    font-weight: 900;
  }
</style>
<div class="text-center p w-react m-m blur" class:white-border={dark} class:dark={!dark} class:white={dark}>
  <div style="display:inline-block">
    <i class="fa fa-gamepad"></i> <button onclick={reset} class="f fake-button" class:white={dark}>Fronds</button>
  </div>
  <hr/>
  <div>
    <button onclick={selectGBA} class:white={dark}>GBA</button>
    <button onclick={selectSNES} class:white={dark}>SNES</button>
    <button onclick={selectN64} class:white={dark}>N64</button>
    <button onclick={selectOLD64} class:white={dark}>Old64</button>
    <button onclick={selectFLASH} class:white={dark}>Flash</button><br/>
    <hr/>
    {#if selected == "NONE"}
      <p style="font-size:12px;" class="no-border" class:gray={!dark} class:white={dark}>
        Start <b>Playing</b> Fronds!<br/>
        Load your own ROM <a href="https://nueot-437a9.web.app/emulate" class:nue-calm={dark} class:calm={!dark} class="no-m">Here</a>!
      </p>
    {:else if selected == "GBA"}
      {#each gba as app,i}
        {#if app[2]}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
          {:else}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&emsp;
        {/if}
      {/each}
    {:else if selected == "SNES"}
      {#each snes as app,i}
        {#if app[2]}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
          {:else}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&emsp;
        {/if}
      {/each}
    {:else if selected == "N64"}
      {#each n64 as app,i}
        {#if app[2]}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
          {:else}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&emsp;
        {/if}
      {/each}
    {:else if selected == "OLD"}
      <p class="small italic">N64 Titles running Neptun to boost performance.</p>
      <hr/>
      {#each old as app,i}
        {#if app[2]}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
          {:else}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&emsp;
        {/if}
      {/each}
    {:else if selected == "FLASH"}
      {#each flash as app,i}
        {#if app[2]}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a><br/>
          {:else}
          <a class="no-underline" class:nue-calm={dark} class:calm={!dark} href={app[1]}>{app[0]}</a>&nbsp;
        {/if}
      {/each}
    {/if}
  </div>
</div>
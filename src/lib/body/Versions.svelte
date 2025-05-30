<script>
    let {dark} = $props();
    let visable = $state(false);
    function toggle(){
      visable = !visable;
    }
    let vers = $state([
      ["Guyot XXIII Rev 1","https://classicmc-studios.github.io/Westonism/old_guyot/xxiii1",true],
      ["Guyot XXIII","#FromNueot"],
      ["Guyot XXII Rev2","https://classicmc-studios.github.io/Westonism/old_guyot/xxii2",true],
      ["Guyot XXII Rev1","https://classicmc-studios.github.io/Westonism/old_guyot/xxii1",true],
      ["Guyot XXII","https://classicmc-studios.github.io/Westonism/old_guyot/xxii"],
      ["Guyot XXI","https://classicmc-studios.github.io/Westonism/old_guyot/xxi"],
      ["Guyot XX","https://classicmc-studios.github.io/Westonism/old_guyot/xx"],
      ["Guyot XIX Rev1","https://classicmc-studios.github.io/Westonism/old_guyot/xix1",true],
      ["Guyot XIX","https://classicmc-studios.github.io/Westonism/old_guyot/xix"],
      ["Guyot XVIII","https://classicmc-studios.github.io/Westonism/old_guyot/xviii"],
      ["Guyot XVII Rev2","https://classicmc-studios.github.io/Westonism/old_guyot/xvii2",true],
      ["Guyot XVII","https://classicmc-studios.github.io/Westonism/old_guyot/xvii"],
      ["Guyot XVI Rev5","https://classicmc-studios.github.io/Westonism/old_guyot/xvi5",true],
      ["Guyot XVI","https://classicmc-studios.github.io/Westonism/old_guyot/xvi"],
      ["Guyot XV Rev2","https://classicmc-studios.github.io/Westonism/old_guyot/xv",true],
      ["Guyot XV","https://classicmc-studios.github.io/Westonism/old_guyot/xv0"],
      ["Guyot XIV Rev2","https://classicmc-studios.github.io/Westonism/old_guyot/xiv2",true],
      ["Guyot XIV Rev1","https://classicmc-studios.github.io/Westonism/old_guyot/xiv1",true],
      ["Guyot XIV","https://classicmc-studios.github.io/Westonism/old_guyot/xiv"],
      ["Guyot XIII","https://classicmc-studios.github.io/Westonism/old_guyot/xiii"],
      ["Guyot XI","https://classicmc-studios.github.io/Westonism/old_guyot/xi+easter"],
      ["Guyot X","https://classicmc-studios.github.io/Westonism/old_guyot/x"],
      ["Guyot v8","https://classicmc-studios.github.io/Westonism/old_guyot/v8"],
      ["Guyot v7","https://classicmc-studios.github.io/Westonism/old_guyot/beta"],
      ["Guyot 0.9","https://guyotjs.github.io/original"],
      ["Guyot 0.5.6","https://classicmc-studios.github.io/Westonism/old_guyot/first"],
      ["Guyot 12%","https://classicmc-studios.github.io/guyot"]
    ]);
  </script>
  <style>
    .w-react{
      display:grid;
      width:min(500px,90%);
      margin-left:50%;
      transform: translate(-50%);
    }
    .contain{
      height: 150px;
      overflow-y: scroll;
      padding: 1px;
      backdrop-filter: blur(10px);
      -wekbkit-backdrop-filter: blur(10px);
    }
    a{margin: 3px;}
    a:hover{font-weight: 900;}
    .calm{text-decoration: none;}
  </style>
  <link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
  <div class="text-center p w-react m-m blur" class:white-border={dark} class:dark={!dark}>
    <div style="display:inline-block">
      <button class="fake-button f hover-bold" class:white={dark} onclick={toggle}> <i class="fa fa-folder-o "></i> Versions </button>
    </div>
    <hr/>
    {#if visable}
      <div class="text-center contain" class:white-border={dark} class:dark={!dark}>
        {#each vers as ver, i}
          <a href={ver[1]} class:calm={!dark} class="no-underline" class:nue-calm={dark}>{ver[0]}</a>
          {#if !ver[2]}<br/>{/if}
        {/each}
      </div>
    {/if}
  </div>
  
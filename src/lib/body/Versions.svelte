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

    let search = $state("");
  </script>
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
    .white-border{
      border:1px solid gray;
      border-radius: 5px;
    }
    .dark{
      border: 1px solid lightgray;
      border-radius: 5px;
    }
    .hover:hover{
      font-weight: 900;
    }
    .contain{
      height: 200px;
      overflow-y: scroll;
      padding: 1px;
      backdrop-filter: blur(10px);
      -wekbkit-backdrop-filter: blur(10px);
    }
    button:not(.fake-button){
          margin:0px;
          padding:2px;
          border: 1px solid rgba(0,0,0,0);
      background-color: rgba(0,0,0,0);
      }
      button:hover:not(.fake-button){
          border:1px solid gray;
          border-radius: 5px;
      }
    hr{
      border-color: rgba(0,0,0,0);
      margin:1px;
    }
    .fake-button{
      background-color: rgba(0,0,0,0);
      border: none;
    }
    a:hover{
      font-weight: 900;
      /* text-decoration: line-through; */
    }
    a{
      margin: 3px;
    }
    .nue-calm{
      color:#49d0a7;
      text-decoration: none;
    }
    .calm{
      text-decoration: none;
    }
  </style>
  <link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
  <div class="text-center p w-react m-m blur" class:white-border={dark} class:dark={!dark}>
    <div style="display:inline-block">
      {#if !visable}
        <button class="fake-button f" class:white={dark} onclick={toggle}> <i class="fa fa-folder-o"></i> Versions </button>
      {:else}
        <button class="fake-button f" class:white={dark} onclick={toggle}> <i class="fa fa-folder-open-o"></i> Versions </button>
      {/if}
    </div>
    <hr/>
    {#if visable}
      <div class="text-center contain`" class:white-border={dark} class:dark={!dark}>
        {#each vers as ver, i}
          <a href={ver[1]} class:calm={!dark} class:nue-calm={dark}>{ver[0]}</a>
          {#if !ver[2]}<br/>{/if}
        {/each}
      </div>
    {/if}
  </div>
  
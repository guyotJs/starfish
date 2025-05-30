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
    ["Doom","./games/doom.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSWT3-NdVALiaYvQkxPIqwNovfdafUjk8C8Mw&s"],
    ["FF 1&2 Advance","https://nueot-437a9.web.app/games/ff12.html",false,"https://i.ebayimg.com/images/g/lR4AAOxyDgRQ9xZD/s-l500.jpg"],
    ["FFV Advance","https://nueot-437a9.web.app/games/ffv.html",true,"http://guyotjs.github.io/ffv.png"],
    ["Leafgreen","https://nueot-437a9.web.app/games/lg.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRNtas7PEu2HTM0nhIUuhkQhDWxhAJ_cS97Nw&s"],
    ["FFIV Advance","https://nueot-437a9.web.app/games/ffivadv.html",false,"https://guyotjs.github.io/fi/ffiv.jpg"],
    ["Mario Kart Super Circut","https://nueot-437a9.web.app/games/mksc.html",true,"https://upload.wikimedia.org/wikipedia/en/thumb/9/90/Super_Circuit.jpg/220px-Super_Circuit.jpg"],
    ["Emerald","https://nueot-437a9.web.app/games/emerald.html",false,"https://upload.wikimedia.org/wikipedia/en/f/f7/PokemonEmeraldBox.jpg"],
    ["Minish Cap","https://nueot-437a9.web.app/games/mc.html",false,"https://guyotjs.github.io/fi/minish.png"],
    ["Spyro","https://nueot-437a9.web.app/games/spyro.html",true,"https://upload.wikimedia.org/wikipedia/en/2/25/Spyro_2_Season_of_Flame_box_art.JPG"],
    ["FFVI Adv","https://nueot-437a9.web.app/games/ffvien.html",false,"https://guyotjs.github.io/fi/ffvi.jpg"],
    ["Kirby Nightmare","https://nueot-437a9.web.app/games/nightmare.html",false,"https://guyotjs.github.io/fi/nightmare.png"]
  ]);
  let snes = $state([
    ["FFIV","https://nueot-437a9.web.app/games/ffiv-snes.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQTb9q77hocujQfDlo9vDb2c6Lq-lp4Nk-gmA&s"],
    ["FFVI (3)","https://nueot-437a9.web.app/games/ffvi-snes.html",false,"https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/fb443c4f-54df-4b53-9e27-632a0af39569/ddb0lq1-2cfd88c1-ca9f-46e6-afbd-966ac7ea8f48.jpg/v1/fill/w_690,h_490,q_75,strp/final_fantasy_vi_snes_usa_cover_art_by_91_mph_ddb0lq1-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9NDkwIiwicGF0aCI6IlwvZlwvZmI0NDNjNGYtNTRkZi00YjUzLTllMjctNjMyYTBhZjM5NTY5XC9kZGIwbHExLTJjZmQ4OGMxLWNhOWYtNDZlNi1hZmJkLTk2NmFjN2VhOGY0OC5qcGciLCJ3aWR0aCI6Ijw9NjkwIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.RXbH0fSeDTbwAXxhG_3hdgfdYTYkVI1giYFZrWWF0VA"],
    ["Link to the Past","https://nueot-437a9.web.app/games/lttp.html",true,"https://upload.wikimedia.org/wikipedia/en/2/21/The_Legend_of_Zelda_A_Link_to_the_Past_SNES_Game_Cover.jpg"],
    ["Super Mario Kart","https://nueot-437a9.web.app/games/smk.html",false,"https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcQ-GuV3eXdrlvNGmkKmlZysitMrUhdtXhkeSHA33rk9Aiy5rmBIm-waS8kPfea0-8eFJ3SKC2KSAAtIObeqyoqqgSt-TjQruQYhtv1k9Ac"],
    ["Yoshi's Island","https://nueot-437a9.web.app/games/yo.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRafZUdJuJY7K3oyAuC80MBZUph6CS2aw-kUw&s"],
    ["Yoshi's Island ROM Hack","https://nueot-437a9.web.app/games/yoshi.html",true,"https://i.ytimg.com/vi/07TPuJPoIFE/sddefault.jpg"],
    ["Super Mario World","https://nueot-437a9.web.app/games/smw.html",false,"https://upload.wikimedia.org/wikipedia/en/3/32/Super_Mario_World_Coverart.png"],
    ["Earthbound","https://nueot-437a9.web.app/games/eb.html",false,"https://imageio.forbes.com/specials-images/imageserve/5eda2a0c0dd0060006207a5a/EarthBound-SNES-cover-art/0x0.jpg?format=jpg&crop=1000,667,x0,y102,safe&width=960"],
    ["Street Fighter 2","https://nueot-437a9.web.app/games/sf2t.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSaqnCD3RR0lWIVg8Sos5P2t1jI7sfTfZq9A1XovaAci4fPg6s:https://i.ebayimg.com/images/g/BCcAAOSwX51kXsBq/s-l1200.jpg&s"],
    ["Donkey Kong Country","https://nueot-437a9.web.app/games/dkc.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQFmY-PKPbnX2eKrgttZQ_eun-uanPGbjTtiLvgAijqL_WsRVE:https://upload.wikimedia.org/wikipedia/en/1/1a/Donkey_Kong_Country_SNES_cover.png&s"],
    ["Super Meteroid","https://nueot-437a9.web.app/games/sm.html",false,"https://i.ebayimg.com/images/g/BRYAAOSw6Hlkp36Q/s-l1200.jpg"],
    ["F-Zero","https://nueot-437a9.web.app/games/f0.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTREmRbmtbh1YW_z4zdaLX4T0O0NkBBSlJrlYFYnLkKLvZ0AHOh:https://upload.wikimedia.org/wikipedia/en/9/9b/SNES_F-Zero_boxart.jpg&s"],
    ["Star Fox","https://nueot-437a9.web.app/games/sf.html",false,"https://i.ebayimg.com/images/g/gfQAAOSwN6xkXr~s/s-l1200.jpg"],
    ["Kirby Superstar","https://nueot-437a9.web.app/games/superkirby.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRNNlG7pWxxsa1sgx3B-4zyLRivPCmiYRQL-2vRj-uu1XR7u4bV:https://i.ebayimg.com/images/g/QNYAAOSwNjNkcUIg/s-l1200.jpg&s"],
    ["Pilotwings","https://nueot-437a9.web.app/games/pilot.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzkhLaQZD1AEsVDhlIop59By-O5j1-VbXe9zY64s3A899qRuo:https://i.ebayimg.com/images/g/ehcAAOSwzKpkoQbG/s-l1200.jpg&s"],
    ["Secret of Mana","https://nueot-437a9.web.app/games/secretom.html",false,"https://i.ebayimg.com/images/g/vMAAAOSwi85dfvZb/s-l1200.png"],
    ["Super Ghouls and Ghosts","https://nueot-437a9.web.app/games/ghouls.html",false,"https://upload.wikimedia.org/wikipedia/en/3/35/GhoulsSNES_boxart.JPG"],
    ["Megaman X","https://nueot-437a9.web.app/games/megamanx.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSOGxbVZfP6Z0zG8tTWB9awOdMohJHQkxJXgnHaagE5-_ntHmHi:https://i.ebayimg.com/images/g/Cd4AAOSwt-NkbB8c/s-l1200.jpg&s"],
    ["Contra 3","https://nueot-437a9.web.app/games/contra3.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTYUdmyhTptKyVm0bodtg6YqSYc60cS_rd0lChnMtf94W2otM4t:https://i.ebayimg.com/images/g/wQ4AAOSw19tkcUnd/s-l1200.jpg&s"],
    ["Kirby Dream Course","https://nueot-437a9.web.app/games/dreamland.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRXYpKXqgluO9PkcxEmoR62RFC2BglQqrgu6ncSfCX5FHeX5vU:https://i.ebayimg.com/images/g/7YcAAOSwzBxkcUJS/s-l1200.jpg&s"],
    ["Super Mario RPG","https://nueot-437a9.web.app/games/mariorpg.html",true,"https://i.ebayimg.com/images/g/trkAAOSwLcJkPy4s/s-l1200.jpg"],
    ["Terranigma","https://nueot-437a9.web.app/games/terranigma.html",false,"https://upload.wikimedia.org/wikipedia/en/4/4b/SNES_Terranigma_cover_art.jpg"]
  ])
  let n64 = $state([
    ["Mario Kart 64","https://nueot-437a9.web.app/games/mk64.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7PXHx1kKq9omDcMGoBy8_RBOnKabqHPDInw&s"],
    ["Super Smash Bros 64","https://nueot-437a9.web.app/games/ssb.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQYvNW3aUj1669uHTkusuClq4OO1EoqVfi-CQ&s"],
    ["Paper Mario","https://nueot-437a9.web.app/games/pm.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRkLAZ2dWnm4imKfkgoQ9aVPlrYLA4WX6h3aQ&s"],
    ["Super Mario 64","https://nueot-437a9.web.app/games/sm64.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoNhpH0BkUa71cwCyqL368zBhrxrID9dLA0Q&s"],
    ["Mario Tennis 64","https://nueot-437a9.web.app/games/mt.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQhD26bj--WgE6sERw9RdH2SYpS3jRqe902arAfykzEF13hCws:https://i.ebayimg.com/images/g/DnIAAOSwXdRkhN6W/s-l1200.jpg&s"],
    ["Star Fox 64","https://nueot-437a9.web.app/games/sf64.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTZ8NQA3Df6kTJwQInDypkk2H1I_URtowxEOg&s"],
    ["Donkey Kong 64","https://nueot-437a9.web.app/games/dk64.html",false,"https://upload.wikimedia.org/wikipedia/en/a/ae/DonkeyKong64CoverArt.jpg"],
    ["Harvest Moon 64","https://nueot-437a9.web.app/games/hm64.html",false,"https://i.ebayimg.com/images/g/Vz4AAOSwYTpkhNyj/s-l1200.jpg"],
    ["Ocarina of Time","https://nueot-437a9.web.app/games/tlozoc.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTmsNoSfiYZ7KimJ-WUJsHe1wny098Pr0yfnHGUKjrbVgDr-gQ:https://i.ebayimg.com/images/g/k7cAAOSwJ19kYC3u/s-l1200.jpg&s"],
    ["Banjo Kazooie","https://nueot-437a9.web.app/games/bk64.html",false,"https://i.ebayimg.com/images/g/1W4AAOSwf2NkYC9O/s-l1200.jpg"],
    ["Quake 64","https://nueot-437a9.web.app/games/quake64.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT2v2_bt0x0bQ-X8RocByx2nHtl09M8FSfMeQ&s"],
    ["Kirby 64","https://nueot-437a9.web.app/games/kirby64.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR7MAcYg1O2vqfQNLuoSzP4M-L--oYODL9o8w&s"],
  ])
  let old = $state([
    ["Ocarina of Time","http://classicmc-studios.github.io/NeptunJS/tlozoc.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTmsNoSfiYZ7KimJ-WUJsHe1wny098Pr0yfnHGUKjrbVgDr-gQ:https://i.ebayimg.com/images/g/k7cAAOSwJ19kYC3u/s-l1200.jpg&s"],
    ["Mario Tennis","http://classicmc-studios.github.io/NeptunJS/mt.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQhD26bj--WgE6sERw9RdH2SYpS3jRqe902arAfykzEF13hCws:https://i.ebayimg.com/images/g/DnIAAOSwXdRkhN6W/s-l1200.jpg&s"],
    ["Mario Kart 64","http://classicmc-studios.github.io/NeptunJS/mk64.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7PXHx1kKq9omDcMGoBy8_RBOnKabqHPDInw&s"]
  ])
  let flash = $state([
    ["Run","https://guyotjs.github.io/flash/games/run.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRudPrRNvfQUbTOHKo-5vK5UTvDEyXZrwfIr0e9s2dqEaUJXo0:https://static.wikia.nocookie.net/run1438/images/8/8b/Level_1_Run_1.png/revision/latest%3Fcb%3D20171118034645&s"],
    ["Bloxorz","https://guyotjs.github.io/flash/games/b.html",false,"https://i.ytimg.com/vi/ba2BJ1jcVFw/sddefault.jpg"],
    ["Breaking the Bank","https://guyotjs.github.io/flash/games/btb.html",true,"https://guyotjs.github.io/fi/btb.png"],
    ["Fancy Pants 1","https://guyotjs.github.io/flash/games/fpa.html",false,"https://img.poki-cdn.com/cdn-cgi/image/quality=78,width=1200,height=1200,fit=cover,f=png/e86e8f057ec357e9b1bc04963a99e752.png"],
    ["Fancy Pants 2","https://guyotjs.github.io/flash/games/fpa2.html",false,"https://img.poki-cdn.com/cdn-cgi/image/quality=78,width=314,height=314,fit=cover,f=auto/61c4ff5c0dbf5ee32e2b19693c9c073d.png"],
    ["Fancy Pants 3","https://guyotjs.github.io/flash/games/fpa3.html",true,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcScOkIaZHMeoUcDwNs_AKYZ8j2wB1NtV1eJxJ62VK0CefYN1p0:https://img.poki-cdn.com/cdn-cgi/image/quality%3D78,width%3D314,height%3D314,fit%3Dcover,f%3Dauto/abc05b37671c22f2c4407e27c6707283.png&s"],
    ["Run 3","https://guyotjs.github.io/flash/games/run3.html",false,"https://guyotjs.github.io/fi/run3.jpg"],
    ["Escaping the Prison","https://guyotjs.github.io/flash/games/etp.html",false,"https://i.ytimg.com/vi/1qaS7MwFRAo/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLA-b_1Pj-NtMbQIHncKaooetmOVfg"],
    ["Stealing the Diamond","https://guyotjs.github.io/flash/games/std.html",true,"https://i.ytimg.com/vi/LRA-xu8CPm0/maxresdefault.jpg"],
    ["Duck Life Treasure Hunt","https://guyotjs.github.io/flash/games/dlth.html",false,"https://img.tapimg.net/market/images/b556fe85ccf6784b7e0d6ca4d8d03c9d.png?imageView2/2/w/720/h/720/q/80/format/jpg/interlace/1/ignore-error/1&t=1"],
    ["Fleeing the Complex","https://guyotjs.github.io/flash/games/ftc.html",false,"https://guyotjs.github.io/fi/ftc.png"],
    ["I'm Outta Here","https://guyotjs.github.io/flash/games/ioh.html",true,"https://i.ytimg.com/vi/FF-wws5PTqs/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AHUBoAC4AOKAgwIABABGEogQyhlMA8=&rs=AOn4CLAomoqCqpBkGWdw5_y4u-2I1z1ceA"],
    ["Infiltrating the Airship","https://guyotjs.github.io/flash/games/ita.html",false,"https://guyotjs.github.io/fi/ita.png"],
    ["Line Rider","https://guyotjs.github.io/flash/games/lr2.html",false,"https://i.ytimg.com/vi/dmBQQ2XtuhU/maxresdefault.jpg"],
    ["Super Mario Flash 2","https://guyotjs.github.io/flash/games/smf2.html",true,"https://i.ytimg.com/vi/IfZjUv6adHg/maxresdefault.jpg"],
    ["Super Smash Flash","https://guyotjs.github.io/flash/games/ssf.html",false,"https://guyotjs.github.io/fi/ssf.png"],
    ["The Binding of Issac","https://guyotjs.github.io/flash/games/tboi.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRWrogB539t0am7IYv3k45tW71GCGM93luojDO4-wkQO-UOkKo:https://i.ytimg.com/vi/TF0NOxM8zKo/maxresdefault.jpg&s"],
    ["The World's Hardest Game","https://guyotjs.github.io/flash/games/twhg.html",true,"https://i.ytimg.com/vi/DJh4QgYgUy0/maxresdefault.jpg"],
    ["Riddle School 1","https://guyotjs.github.io/flash/games/rs1.html",false,"https://guyotjs.github.io/fi/rs.png"],
    ["Riddle School 2","https://guyotjs.github.io/flash/games/rs1.html",false,"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbpEsM5xwbjEmKUuF2bbiwoZxYp5mDDY3dc9xrXmPIOt6CTjs:https://static.wikia.nocookie.net/riddleschool/images/7/7e/Rs2_thumb.jpg/revision/latest%3Fcb%3D20160613062023&s"],
    ["Riddle School 3","https://guyotjs.github.io/flash/games/rs3.html",false,"https://guyotjs.github.io/fi/rs3.png"],
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
  .small{font-size: 12px;}
  .no-m{margin:0;}
  a{margin: 3px;}
  a:hover{font-weight: 900;}
</style>
<div class="text-center p w-react m-m blur" class:white-border={dark} class:dark={!dark} class:white={dark}>
  <div style="display:inline-block">
    <i class="fa fa-gamepad"></i> <button onclick={reset} class="f fake-button" class:white={dark}>Fronds</button>
  </div>
  <hr/>
  <div>
    <button onclick={selectGBA} class:white={dark} class:nin={!dark}>GBA</button>
    <button onclick={selectSNES} class:white={dark} class:nin={!dark}>SNES</button>
    <button onclick={selectN64} class:white={dark} class:nin={!dark}>N64</button>
    <button onclick={selectOLD64} class:white={dark} class:nin={!dark}>Old64</button>
    <button onclick={selectFLASH} class:white={dark} class:nin={!dark}>Flash</button><br/>
    <hr/>
    {#if selected == "NONE"}
      <p style="font-size:12px;" class="no-border" class:gray={!dark} class:white={dark}>
        Start <b>Playing</b> Fronds!<br/>
        Load your own ROM <a href="https://nueot-437a9.web.app/emulate" class:nue-calm={dark} class:calm={!dark} class="no-m">Here</a>!
      </p>
    {:else if selected == "GBA"}
      {#each gba as app,i}
        <a href={app[1]}>
          <img src={app[3]} alt={app[1]} width="150px" style="margin:3px;border-radius:5px;">
        </a>
        {#if app[2]}<br/>{/if}
      {/each}
    {:else if selected == "SNES"}
      {#each snes as app,i}
        <a href={app[1]}>
          <img src={app[3]} alt={app[1]} width="150px" style="margin:3px;border-radius:5px;">
        </a>
        {#if app[2]}<br/>{/if}
      {/each}
    {:else if selected == "N64"}
      {#each n64 as app,i}
        <a href={app[1]}>
          <img src={app[3]} alt={app[1]} width="150px" style="margin:3px;border-radius:5px;">
        </a>
        {#if app[2]}<br/>{/if}
      {/each}
    {:else if selected == "OLD"}
      <p class="small italic">N64 Titles running Neptun to boost performance.</p>
      <hr/>
      {#each old as app,i}
        <a href={app[1]}>
          <img src={app[3]} alt={app[1]} width="150px" style="margin:3px;border-radius:5px;">
        </a>
      {/each}
    {:else if selected == "FLASH"}
      {#each flash as app,i}
        <a href={app[1]}>
          <img src={app[3]} alt={app[1]} width="150px" style="margin:3px;border-radius:5px;">
        </a>
        {#if app[2]}<br/>{/if}
      {/each}
    {/if}
  </div>
</div>
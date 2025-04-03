<script>
  let {dark} = $props();
  let word = $state("Mountain Village")
  let loaction = $state("https://wiki.dominionstrategy.com/images/e/ed/Mountain_Village.jpg");
</script>
<style>
  hr{
    border-color: rgba(0,0,0,0);
    margin:1px;
  }
  .nue-calm{
    color:#49d0a7;
  }
  img{
    width:150px;
    position: absolute;
    z-index: 1;
    left:50%;
    transform: translate(-50%);
    display:none;
  }
  .word:hover + .holder{
    display: block;
  }
  .word{
    user-select: none;
    -webkit-user-select: none;
  }
</style>
<link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
<div class="text-center">
  <b class:gray={!dark} class:white={dark}>Card of the Week</b><br/>
  <hr/>
  <span class="italic underline held" class:nue-calm={dark} class:calm={!dark}>
    <span class="word">{word}</span>
    <img class="holder r border" src={loaction} alt="Marchalnd"/>
  </span>
</div>
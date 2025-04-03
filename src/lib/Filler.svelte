<script>
  let {dark} = $props();
</script>
<style>
  hr{
    border-color: rgba(0,0,0,0);
    margin:1px;
  }
  .dg{
    color:rgb(105, 104, 104);
  }
</style>
<link rel='stylesheet' href="https://guyotjs.github.io/bcss/bc.css"/>
<div class="text-center true-sans" class:gray={!dark} class:white={dark}>
  A <b>Weston</b> Project<br/>
  <hr/>
  Reinvigorating Chromebooks <em class="true-sans">everywhere</em>.
</div>
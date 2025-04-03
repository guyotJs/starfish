<script>
  let {dark} = $props();
</script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
	.white{color:white!important;}
	a{color:black!important;}
	i{
		margin:0px;
		padding:2px;
		border: 1px solid rgba(0,0,0,0);
	}
	i:hover{
		border:1px solid gray;
		border-radius: 5px;
	}
	.opacity{
		display: none;
	}
	.icons{
		margin:5px;
	}
	hr{
		border:none;
		margin-bottom: 15px;
	}
</style>
<div class="text-center icons">
	<a href="https://github.com/guyotJs">
		<i class:white={dark} class="fa fa-github"></i><span class="opacity">Github</span>
	</a>
	&nbsp;&nbsp;
	<a href="https://classicmc-studios.github.io">
		<i class:white={dark} class="fa fa-cube"></i><span class="opacity">Website</span>
	</a>
	&nbsp;&nbsp;
	<a href="mailto: classicmclive+guyot@gmail.com">
		<i class:white={dark} class="fa fa-envelope"></i><span class="opacity">Email</span>
	</a>
	&nbsp;&nbsp;
	<a href="https://snojs.github.io">
		<i class:white={dark} class="fa fa-snowflake-o"></i><span class="opacity">snojs</span>
	</a>
	&nbsp;<hr/>
	<!-- <button><a href="https://twitter.com/WestonSchnee"><i class:white={dark} class="fa fa-twitter"></i></a> -->
</div>
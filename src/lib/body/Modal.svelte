<script>
	let { showModal = $bindable(), header, children,dark } = $props();

	let dialog = $state(); // HTMLDialogElement

	$effect(() => {
		if (showModal) dialog.showModal();
	});
</script>

<!-- svelte-ignore a11y_click_events_have_key_events, a11y_no_noninteractive_element_interactions -->
<dialog
	bind:this={dialog}
	onclose={() => (showModal = false)}
	onclick={(e) => { if (e.target === dialog) dialog.close(); }}
	class="p-m r "
	class:border-white={!dark}
	class:border-dark={dark}
	class:white={dark}
>
	<div>
		{@render header?.()}
		<hr class:hr-white={!dark}
		class:hr-dark={dark}/>
		{@render children?.()}
		<!-- svelte-ignore a11y_autofocus -->
	</div>
</dialog>

<style>
	dialog{
		/* opacity: 0; */
		position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);
		background-color: rgba(0,0,0,0);
		backdrop-filter: blur(15px);
		-webkit-backdrop-filter: blur(15px);
		border:none; 
	}
	hr{
		margin-bottom:7px;
		border-style:dashed;
		border-color:rgb(189, 187, 187);
	}
	.border-white{
		border: 2px dashed rgb(189, 187, 187);
	}
	.border-dark{
		border: 2px dashed rgb(255,255,255,0.2);
	}
	.hr-white{
		border: 1px dashed rgb(189, 187, 187);
	}
	.hr-dark{
		border: 1px dashed rgb(255,255,255,0.2);
	}
	dialog[open] {
		animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
	}
	@keyframes zoom {
		from {
			transform: scale(0.95) translate(-50%,-50%);
		}
		to {
			transform: scale(1) translate(-50%,-50%);
		}
	}
	dialog[open]::backdrop {
		animation: fade 0.2s ease-out;
	}
	@keyframes fade {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
	button {
		display: block;
	}
</style>

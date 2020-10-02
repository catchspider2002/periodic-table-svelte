<script>
	// This property is used by Modal.svelte to pass down the close function
  export let onClose;
</script>

<style>
	button {
		position: absolute;
		top: 1em;
		right: 10px;
		color: white;
		z-index: 5;
		width: 40px;
		background-color:  transparent;
		/* border: 2px solid pink; */
	}
</style>

<button on:click={onClose}>X</button>
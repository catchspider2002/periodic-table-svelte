<script>
	// This property is used by Modal.svelte to pass down the close function
  export let onClose;
</script>

<style>
	button {
		position: absolute;
		top: 5px;
		right: 10px;
		color: white;
		z-index: 5;
		width: 40px;
		background-color:  transparent;
	}
</style>

<button on:click={onClose}>×</button>
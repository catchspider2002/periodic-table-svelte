<script>
	// This property is used by Modal.svelte to pass down the close function
  export let onClose;
</script>

<style>
	button {
		position: absolute;
		top: -15px;
		right: 5px;
		color: white;
		z-index: 5;
		width: 40px;
		font-size: 2em;
		background-color:  transparent;
	}
</style>

<button on:click={onClose}>×</button>
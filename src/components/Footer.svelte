<script>
	import Email from 'svelte-material-icons/Email.svelte';
	import { createEventDispatcher } from 'svelte';
	let dispatch = createEventDispatcher();
	let size = '3em';
	let color = 'black';
	let width = size;
	let height = size;
	let viewBox = '0 0 24 24'
</script>

<footer>
	<button on:click={() => dispatch('tabChange', 'Contact')}>
		<Email {color} {size} {width} {height} {viewBox}/>
	</button>
</footer>

<style>

	button {
		background: none;
		color: inherit;
		border: none;
		padding: 0;
		font: inherit;
		cursor: pointer;
		outline: inherit;
	}
	footer {
		border-top: 3px solid #9A9B9C;
		font-weight: 300;
		padding: 0 1em;
		position: fixed;
		bottom: 0px;
		width: 100%;
		z-index: 1;
		background-color: white;
	}

	@media(max-width:1219px) {
		footer {
			position:relative;
		}
	}

</style>
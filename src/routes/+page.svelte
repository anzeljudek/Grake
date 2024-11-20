<script lang="ts">
	import Card from '$lib/card.svelte';

	let x = 0;
	let y = 1;

	function onClick() {
		x = x * 2;
		y = y + 1;
	}
</script>

<h1 class="text-4xl">Hello world!</h1>

<button class="p-2 bg-blue-500 text-white rounded-lg" on:click={onClick}>
	Kliknil si me {x}-krat
</button>

<Card></Card>

<script lang="ts">
	let dolzina = 0;
	let besedilo =
		'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.';
	let maxDolzina = 100000;
	function urediBesedilo(f: string) {
		switch (f) {
			case 'velike':
				besedilo = besedilo.toUpperCase();
				break;
			case 'male':
				besedilo = besedilo.toLowerCase();
				break;
		}
	}

	function epilepticTrigger() {
		let barva = ['blue', 'green', 'red', 'yellow'];
		let moc = [400, 500, 600, 700];

		return (
			'text-' +
			barva[Math.floor(Math.random() * barva.length)] +
			'-' +
			moc[Math.floor(Math.random() * moc.length)]
		);
	}

	$: {
		dolzina = besedilo.length;
	}
</script>

<p>$: {dolzina}</p>

<p class="text-4xl p-3">Besede</p>
<div class="p-3">
	<textarea
		maxlength={maxDolzina}
		bind:value={besedilo}
		class="border-orange-400 rounded-md border-2"
	></textarea>
	<div>
		<button
			on:click={() => urediBesedilo('velike')}
			class="bg-orange-500 rounded-md border-orange-400"
		>
			velike
		</button>
		<button
			on:click={() => urediBesedilo('male')}
			class="bg-orange-500 rounded-md border-orange-400"
		>
			male
		</button>
	</div>
	<p>{dolzina}/{maxDolzina}</p>
	<div class="flex flex-wrap gap-1 w-1/2">
		{#each besedilo.split(' ') as beseda}
			<span class={epilepticTrigger()}>{beseda}</span>
		{/each}
	</div>
</div>

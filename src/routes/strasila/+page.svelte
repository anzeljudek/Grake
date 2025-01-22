<script lang="ts">
	let stevilo = 1;
	let sodo: boolean;
	let vsota = 0;
	let sezamDeliteljev: number[] = [];
	function jeSodo(num: number) {
		if (num % 2 == 0) return true;
		return false;
	}
	function izpisateljiDeliteljev(num: number) {
		let delitelji: number[] = [];
		for (let i = 1; i < num; i++) {
			if (num % i == 0) delitelji.push(i);
		}
		return delitelji;
	}
	function vsotaDeliteljev(nums: number[]) {
		let sestevek = 0;
		for (const i of nums) {
			sestevek += i;
		}
		return sestevek;
	}

	$: {
		sodo = jeSodo(stevilo);
		sezamDeliteljev = izpisateljiDeliteljev(stevilo);
		vsota = vsotaDeliteljev(sezamDeliteljev);
	}
</script>

<div class="flex p-3 flex-col">
	<div>
		<input min="0" bind:value={stevilo} class="border-2 border-red-500 rounded-md" type="number" />
	</div>

	<div class="">
		<div><p>Strasilo je {sodo ? 'sodo' : 'liho'}</p></div>
		<div>
			<p>Sezam Deliteljev:</p>
			<ul class="flex flex-wrap gap-1">
				{#each sezamDeliteljev as st}
					<li class="">
						{st},
					</li>
				{/each}
				<li class="">{stevilo}</li>
			</ul>
		</div>
		<div><p>Vsota deliteljev je {vsota}</p></div>
		<div><p>Število je popolno {vsota == stevilo ? 'p' : 'n'}</p></div>
	</div>
</div>

<script lang="ts">
	type Task = {
		text: String;
		status: Boolean;
	};
	let new_task: string = '';

	let tasks: Task[] = [
		{
			text: 'Uči se kemijo',
			status: true
		},
		{
			text: 'Še se uči se kemijo',
			status: false
		},
		{
			text: 'Uči se biologijo',
			status: false
		},
		{
			text: 'Igraj igrice',
			status: true
		},
		{
			text: 'Uči se angleščino',
			status: true
		}
	];
	function add() {
		tasks = [
			...tasks,
			{
				text: new_task,
				status: false
			}
		];
	}
</script>

<div>
	<input bind:value={new_task} class="rounded-lg" type="text" />
	<button on:click={add} class="text-orange-500 bg-slate-700 rounded-lg">Grumb</button>
</div>
<div>
	<div class="p-3">
		<h3 class="text-4xl">Zadolžitve</h3>
		{#each tasks as task}
			<p class="text-black-700">
				<button on:click={() => (task.status = !task.status)}>{task.status ? '✅' : '❎'}</button>
				<span class={task.status ? 'text-green-700' : 'text-red-700'}>{task.text}</span>
			</p>
		{/each}
	</div>
</div>

<script lang="ts">
	import { page } from '$app/stores';
	import '../app.css';
</script>

<nav class="w-full p-6 bg-orange-400">
	<div class="flex gap-4">
		<a href="/" class={$page.url.pathname === '/' ? 'font-bold' : ''}>Grub</a>
		<a href="/domov" class={$page.url.pathname === '/domov' ? 'font-bold' : ''}>domov</a>
		<a href="/trgovina" class={$page.url.pathname === '/trgovina' ? 'font-bold' : ''}>trgovina</a>
		<a href="/todo" class={$page.url.pathname === '/todo' ? 'font-bold' : ''}>Zadolžitve</a>
	</div>
</nav>

<div class="w-full h-screen bg-blue-300">
	<slot />
</div>

<script lang="ts">
	export let title: string;
	export let desc: string;
	export let openTodos: number;
	export let classes = '';
</script>

<div class={`card p-8 hover:bg-surface-700 duration-200 ease-in-out ${classes}`}>
	<div class="flex gap-2 flex-col">
		<h1 class="h1 font-black">{title}</h1>
		<p class="text-xl">{desc}</p>
		<p class="italic text-surface-200">{openTodos} open todos</p>
	</div>
</div>

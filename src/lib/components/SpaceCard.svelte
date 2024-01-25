<script lang="ts">
	import type { CssClasses } from '@skeletonlabs/skeleton';

	export let title: string;
	export let desc: string;
	export let openTodos: number;
	export let icon: string = 'fa-solid fa-rocket';
	export let classes: CssClasses = '';
</script>

<div class={`card p-8 hover:bg-surface-700 duration-200 ease-in-out group ${classes}`}>
	<div class="flex gap-2 justify-between">
		<div class="flex flex-col gap-2">
			<h1 class="h1 font-black flex gap-4">
				<i class={`text-2xl md:text-4xl text-surface-200 my-auto ${icon}`}></i>
				{title}
			</h1>
			<p class="text-xl">{desc}</p>
			<p class="italic text-surface-200">{openTodos} open todos</p>
		</div>
		<button class="chip variant-ghost-surface mb-auto aspect-square">
			<i class="fa-solid fa-gear text-lg group-hover:rotate-45 duration-200 ease-in-out"></i>
		</button>
	</div>
</div>

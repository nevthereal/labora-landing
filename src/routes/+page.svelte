<script lang="ts">
	import Todo from '$lib/components/Todo.svelte';

	let completed: boolean;
	$: console.log(completed);
</script>

<div class="w-screen h-[80dvh] flex justify-center text-center items-center">
	<div class="flex flex-col gap-4">
		<h1 class="text-7xl font-black hover:tracking-widest duration-200 ease-in-out">TaskForge</h1>
		<div class="group relative mx-auto">
			<div
				class={`absolute z-10 top-10 text-2xl -left-24 font-bold duration-200 ease-in-out opacity-0 ${!completed ? 'md:group-hover:opacity-100' : ''}`}
			>
				Click me <i class="fa-solid fa-hand-pointer rotate-45"></i>
			</div>
			<Todo
				bind:iconState={completed}
				classes="relative"
				body={"Time to be <span class='bg-gradient-to-bl from-primary-500 to-tertiary-400 bg-clip-text text-transparent'>productive</span>"}
			/>
		</div>
		<a
			href="#about"
			class={`btn variant-ghost-primary mx-auto font-bold ${completed ? 'opacity-100' : 'opacity-0'}`}
			>Find out more</a
		>
	</div>
</div>

<script>
	import Todo from '$lib/components/Todo.svelte';
</script>

<div class="w-screen h-[80dvh] flex justify-center text-center items-center">
	<div class="flex flex-col gap-4">
		<h1 class="text-7xl font-black hover:tracking-widest duration-200 ease-in-out">TaskForge</h1>
		<div class="flex flex-col group">
			<Todo
				classes="mx-auto"
				body={"Time to be <span class='bg-gradient-to-bl from-primary-500 to-tertiary-400 bg-clip-text text-transparent'>productive</span>"}
			/>
		</div>
	</div>
</div>

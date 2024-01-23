<script lang="ts">
	import Todo from '$lib/components/Todo.svelte';

	let completed: boolean;
</script>

<div class="w-screen h-[90dvh] flex justify-center text-center items-center">
	<div class="flex flex-col gap-4">
		<h1 class="text-7xl font-black">Labora.</h1>
		<div class="group relative mx-auto">
			<div
				class={`flex gap-2 absolute z-10 top-12 text-2xl -left-24 font-bold duration-200 ease-in-out opacity-0 ${!completed ? 'md:group-hover:opacity-100' : ''}`}
			>
				<span>Click me</span><i
					class="fa-solid fa-hand-pointer duration-200 ease-in-out group-hover:rotate-45"
				></i>
			</div>
			<Todo
				bind:completed
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
<main>
	<!-- About -->
	<div class="grid grid-cols-2" id="about">
		<div class="p-16">
			<p class="text-lg">
				"Labora" is a latin imperative which means "work hard!" in English. <span
					class="font-bold bg-gradient-to-br from-primary-400 to-tertiary-500 bg-clip-text text-transparent"
					>Labora</span
				> is meant to keep you productive and organized. Our goal is to get productive work accessible
				to everyone. This is why this app is, and probably will be for a long time, a web app.
			</p>
		</div>
		<div class="flex flex-col justify-center items-center gap-1">
			<i
				class="fa-solid fa-book text-3xl bg-gradient-to-br from-primary-400 to-tertiary-500 bg-clip-text text-transparent"
			></i>
			<p class="text-2xl font-serif">
				<span class="font-bold">labora (lat, v.)</span>: work hard!
			</p>
		</div>

		<div class="flex justify-center items-center">
			<h1 class="h1 font-bold">It's simple:</h1>
		</div>
		<div class="p-16 flex">
			<div class="m-auto flex flex-col gap-4">
				<h1 class="h2 font-bold">
					A <span
						class="font-bold bg-gradient-to-br from-primary-400 to-tertiary-500 bg-clip-text text-transparent"
						>good</span
					> todo app
				</h1>
				<ul class="flex flex-col gap-4">
					<Todo body="Removes all distractions" completed={true} />
					<Todo body="Keeps you organized" completed={true} />
					<Todo body="Keeps you focused" completed={true} />
					<Todo body="Bloats you with unneeded features" />
				</ul>
			</div>
		</div>
	</div>
</main>

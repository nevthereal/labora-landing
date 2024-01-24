<script lang="ts">
	import SpaceCard from '$lib/components/SpaceCard.svelte';
	import Todo from '$lib/components/Todo.svelte';

	let completed: boolean;
</script>

<svelte:head>
	<title>Labora</title>
	<meta
		name="description"
		content="A powerful todo application that keeps you productive and focused"
	/>
</svelte:head>

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
				body={"Time to be <span class='gradient-text'>productive</span>"}
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
	<section class="grid grid-cols-2" id="about">
		<div class="p-16">
			<p class="text-lg">
				"Labora" is a latin imperative which means "work hard!" in English. <span
					class="font-bold gradient-text">Labora</span
				> is meant to keep you productive and organized. Our goal is to get productive work accessible
				to everyone. This is why this app is, and probably will be for a long time, a web app.
			</p>
		</div>
		<div class="flex flex-col justify-center items-center gap-1">
			<i class="fa-solid fa-book text-3xl gradient-text"></i>
			<p class="text-2xl font-serif">
				<span class="font-bold">labora (lat, v.)</span>: work hard!
			</p>
		</div>
	</section>

	<section class="grid grid-cols-2">
		<div class="flex justify-center items-center">
			<h1 class="h1 font-bold">It's simple:</h1>
		</div>
		<div class="p-16 flex">
			<div class="m-auto flex flex-col gap-4">
				<h1 class="h2 font-bold">
					A <span class="font-bold gradient-text">good</span> todo app
				</h1>
				<ul class="flex flex-col gap-4">
					<Todo body="Removes all distractions" completed={true} />
					<Todo body="Keeps you organized" completed={true} />
					<Todo body="Keeps you focused" completed={true} />
					<Todo body="Bloats you with unneeded features" />
				</ul>
			</div>
		</div>
	</section>

	<section class="grid grid-cols-2">
		<div class="m-16">
			<p class="text-lg">
				We keep you organized with using <span class="gradient-text">Spaces</span>. Spaces are like
				little containers which carry tasks.
			</p>
		</div>
		<div class="m-8">
			<SpaceCard title="This is a space" desc="A place for your todos." openTodos={3} />
		</div>
	</section>
</main>

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
	<section class="grid grid-cols-1 xl:grid-cols-2" id="about">
		<div class="flex justify-center">
			<p class="text-lg w-[60%] my-auto">
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

	<section class="my-16">
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

	<section class="grid grid-cols-1 xl:grid-cols-2">
		<div class="m-16 flex flex-col gap-4">
			<SpaceCard title="School" desc="This is a space." openTodos={3} icon="fa-solid fa-school" />
			<SpaceCard
				title="Development"
				desc="A place for your tasks."
				openTodos={5}
				icon="fa-solid fa-code"
			/>
		</div>
		<div class="flex">
			<p class="text-xl m-auto w-[60%]">
				We keep you organized with using <span class="gradient-text">Spaces</span>. Spaces are like
				little containers which carry tasks.
			</p>
		</div>
	</section>

	<section class="xl:max-w-[60%] max-w-[90%] mx-auto my-16">
		<h1 class="h1 font-bold">Let's summarize:</h1>
		<div class="grid grid-cols-1 xl:grid-cols-3 gap-4 my-8">
			<div class="bento-box col-span-2">
				<h1 class="h1 font-black mx-auto gradient-text">Web-Based</h1>
				<p class="mx-auto text-xl">Accessible for everyone</p>
			</div>
			<div class="bento-box">
				<h1 class="h1 font-black mx-auto gradient-text">0</h1>
				<p class="mx-auto text-xl">Years of experience*</p>
			</div>
			<div class="col-span-3 grid grid-cols-2 gap-4">
				<div class="bento-box">
					<h2 class="h2 font-bold gradient-text m-auto">Stay organized</h2>
					<p class="m-auto">
						Stay in focus thanks to <span class="gradient-text">spaces</span>
					</p>
				</div>
				<div class="bento-box">
					<h2 class="h2 font-bold gradient-text m-auto">Stay Happy</h2>
					<p class="m-auto">With daily habits</p>
				</div>
			</div>
			<div class="bento-box">
				<h2 class="h2 font-bold gradient-text m-auto">Affordable</h2>
				<p class="m-auto">Giving you a generous free tier</p>
			</div>
			<div class="col-span-2 bento-box">
				<h1 class="h1 font-bold gradient-text m-auto">Get it done</h1>
				<p class="m-auto text-lg">
					For a quick entry just press <kbd class="kbd">ctrl + E</kbd>
				</p>
			</div>
		</div>
		<p>*yet</p>
	</section>

	<section class="my-8 flex justify-center">
		<div class="card p-12">
			<h2 class="h2 font-bold mb-4">Sign up for our newsletter</h2>
			<div class="flex flex-col gap-4">
				<div>
					<label for="email">Email</label>
					<input type="email" name="email" class="input" />
				</div>
				<div>
					<label for="how">How did you hear from us?</label>
					<select name="how" class="select">
						<option value="yt">YouTube</option>
						<option value="tw">Twitter</option>
						<option value="friend">A friend</option>
						<option value="other">Other</option>
					</select>
				</div>
				<button class="btn variant-ghost-primary mx-auto">Sign Up!</button>
			</div>
		</div>
	</section>
</main>

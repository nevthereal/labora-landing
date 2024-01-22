<script lang="ts">
	let iconState = false;

	const toggleIcon = () => {
		iconState = !iconState;
	};
</script>

<div class="w-screen h-[80dvh] flex justify-center text-center items-center">
	<div class="flex flex-col gap-4">
		<h1 class="text-7xl font-black hover:tracking-widest duration-200 ease-in-out">TaskForge:</h1>
		<div class="flex flex-col group">
			<div class="card flex p-4 justify-center pr-5 gap-4 items-center mx-auto">
				<button class="btn" on:click={() => toggleIcon()}
					><i class={`${!iconState ? 'fa-regular' : 'fa-solid'} fa-circle-check text-2xl`}
					></i></button
				>
				<p class={`font-bold text-2xl ${iconState ? 'line-through' : ''}`}>
					Time to be <span
						class="bg-gradient-to-bl from-primary-500 to-tertiary-400 bg-clip-text text-transparent"
						>productive</span
					>
				</p>
			</div>
			{#if !iconState}
				<p
					class="text-2xl text-left ml-11 font-bold opacity-0 group-hover:opacity-100 duration-200 ease-in-out"
				>
					<i class="fa-solid fa-hand-pointer"></i> Click me
				</p>
			{:else}
				<a href="#about" class="text-2xl font-semibold">Sounds good?</a>
			{/if}
		</div>
	</div>
</div>

<main id="about">Hello</main>

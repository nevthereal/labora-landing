<script lang="ts">
	import { getModalStore, type CssClasses } from '@skeletonlabs/skeleton';

	export let classes: CssClasses = '';

	const modalStore = getModalStore();
</script>

<div class={`card p-16 ${classes}`}>
	<div class="flex gap-4 mb-6">
		<i class="fa-solid fa-square-plus text-2xl md:text-4xl"></i>
		<h2 class="h2 font-bold">Create a quick entry</h2>
	</div>
	<form class="flex flex-col gap-4" on:submit|preventDefault={() => modalStore.close()}>
		<div>
			<label for="task">Task</label>
			<input class="input" type="text" name="task" />
		</div>
		<div>
			<label for="desc">Additional details (optional)</label>
			<input class="input" type="text" name="desc" />
		</div>
		<button class="btn variant-ghost-primary mx-auto">Add</button>
	</form>
</div>

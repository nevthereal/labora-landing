<script lang="ts">
	export let classes: string = '';
	export let body: string;
	export let completed = false;

	const toggleIcon = () => {
		completed = !completed;
	};
</script>

<li class={`flex card p-4 items-center pr-9 ${classes}`}>
	<button class="btn" on:click={() => toggleIcon()}
		><i class={`${!completed ? 'fa-regular' : 'fa-solid'} fa-circle-check text-2xl`}></i></button
	>
	<p class={`font-bold text-2xl ${completed ? 'line-through' : ''}`}>
		{@html body}
	</p>
</li>

<script lang="ts">
	export let classes: string;
	export let body: string;
	export let iconState = false;

	const toggleIcon = () => {
		iconState = !iconState;
	};
</script>

<li class={`flex card justify-between p-4 items-center ${classes}`}>
	<button class="btn" on:click={() => toggleIcon()}
		><i class={`${!iconState ? 'fa-regular' : 'fa-solid'} fa-circle-check text-2xl`}></i></button
	>
	<p class={`font-bold text-2xl ${iconState ? 'line-through' : ''}`}>
		{@html body}
	</p>
</li>

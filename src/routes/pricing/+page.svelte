<script lang="ts">
	const tiers: PricingTier[] = [
		{
			name: 'Free',
			price: 'Free',
			spaces: 3,
			cloud: true
		},
		{
			name: 'Premium',
			price: 5,
			spaces: 'Unlimited',
			cloud: true
		}
	];
</script>

<main class="flex">
	{#each tiers as tier}
		<div class="card p-12">
			<h1></h1>
		</div>
	{/each}
</main>

<script lang="ts">
	import { Calendar } from 'bits-ui';
	export let value;
</script>

<Calendar.Root let:months let:weekdays class="input p-4">
	<Calendar.Header class="mb-4 flex justify-center gap-4">
		<Calendar.PrevButton><i class="fa-solid fa-arrow-left"></i></Calendar.PrevButton>
		<Calendar.Heading><span class="font-bold">Select Date</span></Calendar.Heading>
		<Calendar.NextButton><i class="fa-solid fa-arrow-right"></i></Calendar.NextButton>
	</Calendar.Header>

	{#each months as month}
		<Calendar.Grid class="mx-auto">
			<Calendar.GridHead>
				<Calendar.GridRow>
					{#each weekdays as day}
						<Calendar.HeadCell>
							{day}
						</Calendar.HeadCell>
					{/each}
				</Calendar.GridRow>
			</Calendar.GridHead>
			<Calendar.GridBody>
				{#each month.weeks as weekDates}
					<Calendar.GridRow>
						{#each weekDates as date}
							<Calendar.Cell {date} class="">
								<Calendar.Day let:selected {date} month={month.value} />
							</Calendar.Cell>
						{/each}
					</Calendar.GridRow>
				{/each}
			</Calendar.GridBody>
		</Calendar.Grid>
	{/each}
</Calendar.Root>

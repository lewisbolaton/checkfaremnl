<template>
	<div class="entry">
		<EntryPicker />
		<span>&mdash;&nbsp;to&nbsp;&mdash;</span>
		<EntryPicker />
		<!--
		<select>
			<option>Consectetur</option>
			<option>Adipiscing</option>
			<option>Elit</option>
		</select>
		-->
		<div>
			<label for="baggage">Do you have baggage</label>
			<input type="checkbox" id="baggage" />

		</div>

	</div>
</template>

<style scoped>
	div.entry	{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
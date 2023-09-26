<template>
	<div class="entry">
		<EntryPicker :list="stations.map(s => s.name)"/>
		<span>&mdash;&nbsp;to&nbsp;&mdash;</span>
		<EntryPicker :list="stations.map(s => s.name)"/>
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

<script setup>
	import data from "public/mrt3.json";
	
	const stations = data.stations;
</script>

<style scoped>
	div.entry	{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
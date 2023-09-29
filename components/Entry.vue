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
	import data_lrt2 from "~/data/lrt2.json";
	import data_mrt3 from "~/data/mrt3.json";

	var stations = [];

	const route = useRoute();

	if (route.path.substring(1) === "lrt2") {
		stations = data_lrt2.stations;
	} else if (route.path.substring(1) === "mrt3") {
		stations = data_mrt3.stations;
	}
</script>

<style scoped>
	div.entry	{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
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
		<EntryToggle />
		<Check />
	</div>
</template>

<script setup>
	import data_lrt2 from "~/data/lrt2.json";
	import data_mrt3 from "~/data/mrt3.json";
	import data_lrt1 from "~/data/lrt1.json";

	const route = useRoute();
	let stations = [];

	if (route.path.substring(1) === "lrt2") {
		stations = data_lrt2.stations;
	} else if (route.path.substring(1) === "mrt3") {
		stations = data_mrt3.stations;
	} else if (route.path.substring(1) === "lrt1") {
		stations = [...data_lrt1.stations].reverse();
	}
</script>

<style scoped>
	div.entry	{
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 0.8rem;

	}

	div.entry > span {
		margin: 0.33rem 0;
		font-size: 0.85em;
		line-height: 1;
		font-style: italic;
	}
</style>
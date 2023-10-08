<template>
	<div class="entry">
		<EntryPicker :list="stations.map(s => s.name)" ref="originpicker"/>
		<span>&mdash;&nbsp;to&nbsp;&mdash;</span>
		<EntryPicker :list="stations.map(s => s.name)" ref="destpicker"/>
		<!--
		<select>
			<option>Consectetur</option>
			<option>Adipiscing</option>
			<option>Elit</option>
		</select>
		-->
		<EntryToggle />
		<Check @check="getPickerIndices" />
	</div>

	<!-- BEGIN DRAFT
	<div>
		<select id="browsers">
  			<option value="Chrome">Chrome</option>
  			<option value="Firefox">Firefox</option>
  			<option value="Opera">Opera</option>
  			<option value="Safari">Safari</option>
  			<option value="Microsoft Edge">Edge</option>
		</select>

		<button id="slcbtn">Select browser</button>
	</div>
	END DRAFT -->
</template>

<script setup>
	import data_lrt2 from "~/data/lrt2.json";
	import data_mrt3 from "~/data/mrt3.json";
	import data_lrt1 from "~/data/lrt1.json";

	const route = useRoute();
	let stations = [];
	
	const originpicker = ref(null);
	const destpicker = ref(null);

	if (route.path.substring(1) === "lrt2") {
		stations = data_lrt2.stations;
	} else if (route.path.substring(1) === "mrt3") {
		stations = data_mrt3.stations;
	} else if (route.path.substring(1) === "lrt1") {
		stations = [...data_lrt1.stations].reverse();
	}

	const getPickerIndices = () => {
		originpicker.value.getScrollIndex();
		destpicker.value.getScrollIndex();
	}

	/* BEGIN DRAFT
	onMounted(() => {
		const button = document.querySelector("button#slcbtn");
		const browserInput = document.querySelector("select#browsers");

		button.addEventListener("click", () => {
		  try {
		    browserInput.showPicker();
		    console.log("picker shown")
		  } catch (error) {
		    // Fall back to another picker mechanism
		    console.log(error);
		  }
		});
	});
	END DRAFT */
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
<template>
	<div class="picker">
		<ol ref="pickerlist">
			<li v-for="s in props.list">{{ s.name }}</li>
		</ol>
		<div class="blurlayers">
			<div></div><div></div>
		</div>
	</div>
</template>

<script setup>
	import { onMounted } from 'vue';

	const props = defineProps(['list']);
	const pickerlist = ref(null);

	
	const getScrollIndex = () => {
		let listInstanceRect = pickerlist.value.getBoundingClientRect();
		let midPoint = (listInstanceRect.bottom + listInstanceRect.top) / 2;

		let items = pickerlist.value.children;
		let itemKeys = Object.keys(items);

		let stationCode  = props.list[0].code;
		itemKeys.every(i => {
			let top = items[i].getBoundingClientRect().top;
			let bottom = items[i].getBoundingClientRect().bottom;
			if (bottom > midPoint && midPoint > top) {
				stationCode = props.list[i].code;
				return false;
			}
			return true;
		});
		return stationCode;
	}

	defineExpose({ getScrollIndex });
	
	onMounted(() => {
		let listInstanceRect = pickerlist.value.getBoundingClientRect();
		let midPoint = (listInstanceRect.bottom + listInstanceRect.top) / 2;

		let items = pickerlist.value.children;
		let itemKeys = Object.keys(items);
		
		itemKeys.forEach(i => {
			let top = items[i].getBoundingClientRect().top;
			let bottom = items[i].getBoundingClientRect().bottom;
			if (bottom > midPoint && midPoint > top) {
				console.log("Found at " + i);
			}
		});
	})
</script>

<style scoped>
	/* Remove default styles */
	ol, li {
		margin: 0;
		padding: 0;
		text-align: center;
	}

	ol {
		list-style: none;
	}

	.picker > ol {
		background-color: yellow;
		border: 1px solid silver;
		width: 92vw;

		overflow-y: scroll;
		height: 2.8rem;

		border-radius: 8px;
		background-color: #333333;
		color: white;

		scroll-snap-type: y mandatory;
	}

	.picker > ol > li {
		scroll-snap-align: center;
	}

	li:first-child { margin-top: 2.8rem }
	li:last-child { margin-bottom: 2.8em }

	.picker {
		display: flex;
	}

	.blurlayers {
		width: 92%;
		height: 2.8em;
		position: absolute;
		z-index: 1;
		opacity: 60%;
		border: 1px solid transparent;


		display: flex;
		flex-direction: column;
		justify-content: space-between;
		pointer-events: none;
	}

	.blurlayers > div {
		height: 0.8em;
		background-color: #333333;
		opacity: 67%;
	}

	.blurlayers > div:first-child { border-radius: 8px 8px 0 0 }
	.blurlayers > div:last-child { border-radius: 0 0 8px 8px }
	
</style>
<template>
<button @click="handleClick">Check</button>
</template>


<script setup>
const emit = defineEmits(['check']);

const handleClick = () => {
	emit('check');
}
</script>


<style scoped>
	/* Remove default styles */
	button {
		background-color: #100F0F;
		color: #CECDC3;
		border: none;
		margin: 0;
		padding: 0.5em 1.5em;
		text-align: inherit;
		font: inherit;
		border-radius: 0;
		appearance: none;
		border-radius: 8px;
		border: 1px solid #CECDC3;

		transition: background-color 0.5s;
	}

	button:hover {
		cursor: pointer;
		background-color: #282726;
	}
</style>
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
		background-color: #879a39;
		border: none;
		margin: 0;
		padding: 0;
		text-align: inherit;
		font: inherit;
		border-radius: 0;
		appearance: none;
	}
</style>
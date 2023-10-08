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

</style>
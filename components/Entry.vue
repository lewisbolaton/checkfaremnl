<template>
	<div class="entry">
		<select>
			<option>Lorem</option>
			<option>Ipsum Dolor</option>
			<option>Sit Amet</option>
		</select>
		<span>&mdash;&nbsp;to&nbsp;&mdash;</span>
		<select>
			<option>Consectetur</option>
			<option>Adipiscing</option>
			<option>Elit</option>
		</select>
		
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
<template>
	<div>
		<p> {{ firstValue }} {{ operation }} {{ secondValue }} = {{ result }}</p>
	</div>
</template>


<script>
export default {
	name: 'CalculationResult',
	props: {
		firstValue: Number,
		operation: String,
		secondValue: Number,
		result: Number
	}
}
</script>

<style></style>
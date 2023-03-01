<script >
import ButtonInput from './components/ButtonInput.vue';


export default {
	name: 'App',
	data() {
		return {
			historyOperation: [],
			currentCalculation: '0',
			lastOperation: '0'
		}
	},
	methods: {
		allClear() {
			this.currentCalculation = '0'
			this.lastOperation = '0'
		},
		doDelete() {
			console.log(this.currentCalculation)
			if (this.currentCalculation !== '0') {
				this.currentCalculation = this.currentCalculation.toString().slice(0, -1)
			}
			if (this.currentCalculation = '') {
				this.currentCalculation = '0'
			}
		}

	}



}







</script>
<template>
	<div class="flex h-full w-full justify-between space-x-2 text-gray-300">
		<ButtonInput class="btn-primary" symbols="AC" @click="allClear()" />
		<button class="btn-primary" symbols="DEL" @click="doDelete()" />
		<button class="btn-primary" symbols="%" @click="percentage()" />
		<button class="btn-operation" symbols="/" @click="division()" />
	</div>

	<div>
		<button class="btn-number" symbols="7" @click="inputValue(7)" />
		<button class="btn-number" symbols="8" @click="inputValue(8)" />
		<button class="btn-number" symbols="9" @click="inputValue(9)" />
		<button class="btn-operation" symbol="X" @click="multiplication()" />
	</div>

	<div>
		<button class="btn-number" symbol="4" @click="inputValue(4)" />
		<button class="btn-number" symbol="5" @click="inputValue(5)" />
		<button class="btn-number" symbol="6" @click="inputValue(6)" />
		<button class="btn-operation" symbol="-" @click="subtraction()" />
	</div>

	<div>
		<button class="btn-number" symbol="1" @click="inputValue(1)" />
		<button class="btn-number" symbol="2" @click="inputValue(2)" />
		<button class="btn-number" symbol="3" @click="inputValue(3)" />
		<button class="btn-operation" symbol="+" @click="addition()" />
	</div>

	<div>
		<button class="btn-number" symbol="0" @click="inputValue(0)" />
		<button class="btn-symbol" symbol="." @click="inputValue('.')" />
		<button class="btn-operation" symbol="=" @click="calculate()" />
	</div>
</template>






























<style scoped>
header {
	line-height: 1.5;
}






























.logo {
	display: block;
	margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
	header {
		display: flex;
		place-items: center;
		padding-right: calc(var(--section-gap) / 2);
	}

	.logo {
		margin: 0 2rem 0 0;
	}

	header .wrapper {
		display: flex;
		place-items: flex-start;
		flex-wrap: wrap;
	}
}
</style>

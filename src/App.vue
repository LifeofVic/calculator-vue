<script >
import ButtonInput from './components/ButtonInput.vue';


export default {
	name: "App",
	data() {
		return {
			historyOperation: [],
			currentCalculation: "0",
			lastOperation: "0"
		};
	},
	methods: {
		allClear() {
			this.currentCalculation = "0";
			this.lastOperation = "0";
		},
		doDelete() {
			console.log(this.currentCalculation);
			if (this.currentCalculation !== "0") {
				this.currentCalculation = this.currentCalculation.toString().slice(0, -1);
			}
			if (this.currentCalculation = "") {
				this.currentCalculation = "0";
			}
		}
	},
	components: { ButtonInput }
}

</script>

<template>
	<div class="flex h-full w-full justify-between space-x-2 text-gray-300">
		<Button-input class="btn-primary" symbols="AC" @click="allClear()" />
		<Button-input class="btn-primary" symbols="<-DEL" @click="doDelete()" />
		<Button-input class="btn-primary" symbols="%" @click="percentage()" />
		<Button-input class="btn-operation" symbols="/" @click="division()" />
	</div>

	<div class="flex h-full w-full justify-between space-x-2 text-gray-300">
		<Button-input class="btn-number" symbols="7" @click="inputValue(7)" />
		<Button-input class="btn-number" symbols="8" @click="inputValue(8)" />
		<Button-input class="btn-number" symbols="9" @click="inputValue(9)" />
		<Button-input class="btn-operation" symbols="X" @click="multiplication()" />
	</div>

	<div>
		<Button-input class="btn-number" symbols="4" @click="inputValue(4)" />
		<Button-input class="btn-number" symbols="5" @click="inputValue(5)" />
		<Button-input class="btn-number" symbols="6" @click="inputValue(6)" />
		<Button-input class="btn-operation" symbols="-" @click="subtraction()" />
	</div>

	<div>
		<Button-input class="btn-number" symbols="1" @click="inputValue(1)" />
		<Button-input class="btn-number" symbols="2" @click="inputValue(2)" />
		<Button-input class="btn-number" symbols="3" @click="inputValue(3)" />
		<Button-input class="btn-operation" symbols="+" @click="addition()" />
	</div>

	<div>
		<Button-input class="btn-number" symbols="0" @click="inputValue(0)" />
		<Button-input class="btn-symbol" symbols="." @click="inputValue('.')" />
		<Button-input class="btn-operation" symbols="=" @click="calculate()" />
	</div>
</template>



<style scoped></style>

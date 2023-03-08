<script >
import ButtonInput from './components/ButtonInput.vue';
import CalcResult from './components/CalcResult.vue';

export default {
	name: "App",
	data() {
		return {
			historyOperation: [],
			result: [],
			lastOperation: "0",
			firstValue: 0,
			secondValue: 0,
		};
	},
	methods: {
		allClear() {
			this.result = "";
			this.lastOperation = "";
			this.firstValue = "";
			this.secondValue = "";
			;
		},
		doDelete() {
			console.log(this.currentCalculation);
			if (this.currentCalculation !== "0") {
				this.currentCalculation = this.currentCalculation.toString().slice(0, -1);
			}
			if (this.currentCalculation = "") {
				this.currentCalculation = "0";
			}
		},
		inputValue(Number) {
			if (this.lastOperation == "") {
				this.firstValue += (Number);
			}
			else if (this.lastOperation == '/' || 'X' || '-' || '+') {
				this.secondValue += Number;
			}
		}, calculate() {
			if (this.lastOperation == '/') {
				this.result += (Number(this.firstValue) / Number(this.secondValue))
				this.historyOperation += ['test', 'test']
			}
			else if (this.lastOperation == 'X') {
				this.result += ((this.firstValue) * (this.secondValue))
				this.historyOperation.push({ firstValue: this.firstValue, operation: this.lastOperation, secondValue: this.secondValue, result: this.result })
			}
		},
		division() {
			this.lastOperation = '/';
		},
		multiplication() {
			this.lastOperation = 'X';
		},
		subtraction() {
			this.lastOperation = '-';
		},
		addition() {
			this.lastOperation = '+';
		}
	},
	components: { ButtonInput, CalcResult }
}

</script>

<template>
	<div>
		<p>first Number: {{ firstValue }}</p>
		<p>operation: {{ lastOperation }}</p>
		<p>Second Number: {{ secondValue }}</p>
		<p> result: {{ result }}</p>
		<p> historyOperation: {{ historyOperation }}</p>
	</div>

	<div class="container">
		<div class="row-1">
			<Button-input class="btn-primary" symbols="AC" @click="allClear()" />
			<Button-input class="btn-primary" symbols="DEL" @click="doDelete()" />
			<Button-input class="btn-operation" symbols="/" @click="division()" />
		</div>

		<div class="row-2">
			<Button-input class="btn-number" symbols="7" @click="inputValue(7)" />
			<Button-input class="btn-number" symbols="8" @click="inputValue(8)" />
			<Button-input class="btn-number" symbols="9" @click="inputValue(9)" />
			<Button-input class="btn-operation" symbols="X" @click="multiplication()" />
		</div>

		<div class="row-3">
			<Button-input class="btn-number" symbols="4" @click="inputValue(4)" />
			<Button-input class="btn-number" symbols="5" @click="inputValue(5)" />
			<Button-input class="btn-number" symbols="6" @click="inputValue(6)" />
			<Button-input class="btn-operation" symbols="-" @click="subtraction()" />
		</div>

		<div class="row-4">
			<Button-input class="btn-number" symbols="1" @click="inputValue(1)" />
			<Button-input class="btn-number" symbols="2" @click="inputValue(2)" />
			<Button-input class="btn-number" symbols="3" @click="inputValue(3)" />
			<Button-input class="btn-operation" symbols="+" @click="addition()" />
		</div>

		<div class="row-5">
			<Button-input class="btn-number" symbols="0" @click="inputValue(0)" />
			<Button-input class="btn-number" symbols="." @click="inputValue('.')" />
			<Button-input class="btn-calculate" symbols="=" @click="calculate()" />
		</div>
	</div>
</template>



<style scoped></style>

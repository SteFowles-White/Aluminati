<template>
	<div class="container">
		<div
			v-for="number in sortNumberHandler"
			:id="'number-' + number"
			:key="number"
			@mouseover="hoverDivisorsNumberHandler(number)"
			@mouseout="resetHandler"
		>
			<div v-if="isDivisor(number)" class="number active">
				{{ number }}
			</div>
			<div v-else class="number">
				{{ number }}
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "Number",
	props: {
		maxLimit: {
			type: Number,
			required: true,
		},
	},
	data() {
		return {
			divisorNumbers: [],
		};
	},
	computed: {
		sortNumberHandler() {
			let numbers = [];
			for (let i = 1; i <= this.maxLimit; i++) {
				numbers = [...numbers, i];
			}
			return numbers.sort((a, b) => a - b);
		},
	},
	methods: {
		hoverDivisorsNumberHandler(number) {
			for (let i = 1; i <= this.maxLimit; i++) {
				if (number % i === 0) {
					this.divisorNumbers.push(i);
				}
			}
		},
		resetHandler() {
			this.divisorNumbers = [];
		},
		isDivisor(number) {
			return this.divisorNumbers.includes(number);
		},
	},
};
</script>

<style scoped>
.container {
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	width: 100vw;
	padding-top: 10px;
}

.number {
	padding: 5px;
	background-color: #d3d3d3;
	margin: 5px;
}

.active {
	background-color: #ff0000;
}
</style>

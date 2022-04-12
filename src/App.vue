<template>
	<div id="app">
		<label for="number">Type in the number here</label>
		<input
			id="number"
			type="number"
			v-model="limit"
			@input="inputHandler"
			max="100"
			min="1"
		/>
		<Numbers :maxLimit="getLimit" />
	</div>
</template>

<script>
import Numbers from "@/components/Numbers";

export default {
	name: "App",
	components: { Numbers },
	data() {
		return {
			limit: 100,
		};
	},
	methods: {
		inputHandler(e) {
			if (e.target.value > 100) {
				this.limit = 100;
				this.error = true;
			}
		},
	},
	computed: {
		getLimit() {
			return parseInt(this.limit);
		},
	},
};
</script>
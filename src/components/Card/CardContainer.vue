<script setup>
import Card from "./Card.vue";
const props = defineProps(["data"]);
</script>

<template>
	<div class="card--container">
		<Card v-for="cardData in data" :cardData="cardData" />
	</div>
</template>

<style lang="scss">
.card--container {
	width: 100%;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	padding: 0px 0px 0px 30px;

	@media (max-width: 1500px) {
		grid-template-columns: repeat(2, 1fr);
	}

	@media (max-width: 1000px) {
		grid-template-columns: repeat(1, 1fr);
	}
}
</style>

<script setup>
	import CardItem from './CardItem.vue';
	import ProjectData from "../../assets/data/ProjectData.json";
</script>

<template>
	<div class="card--container">
		<CardItem v-for=" data in ProjectData " :data="data" />
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
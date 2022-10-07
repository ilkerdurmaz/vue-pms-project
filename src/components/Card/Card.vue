<script setup>
import CardItem from './CardItem.vue';

</script>
<template>
	<div class="card--container">
		<CardItem v-for="i in 9" />
	</div>
</template>
<style lang="scss">

	.card--container {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		padding: 0px 0px 0px 30px;

		@media (max-width: 1450px) {
			grid-template-columns: repeat(2, 1fr);
		}

		@media (max-width: 480px) {
			grid-template-columns: repeat(1, 1fr);
		}



	}
</style>
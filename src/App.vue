<script setup>
import CardCounter from './components/Card/CardCounter.vue'
</script>

<template>

	<div class="counter-group">
		<CardCounter :data="{number : 14, name : 'Task'}"></CardCounter>
		<CardCounter :data="{number : 1, name : 'Members'}"></CardCounter>
	</div>


</template>

<style lang="scss">
.counter-group {
	display: flex;
	flex-wrap: wrap;
	align-items: center;
	justify-content: center;
}


</style>

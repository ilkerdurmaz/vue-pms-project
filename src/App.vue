<script setup>
import CardCounter from './components/Card/CardCounter.vue'
import Card from './components/Card/Card.vue';
</script>

<template>
	<Card />
	<!-- <div class="counter-group">
		<CardCounter :data="{number : 14, name : 'Task'}"></CardCounter>
		<CardCounter :data="{number : 1, name : 'Members'}"></CardCounter>
	</div> -->
</template>

<!-- <template>
	<div>
		
	</div>


</template> -->

<style lang="scss">
.counter-group {
	display: flex;
	flex-wrap: wrap;
	align-items: center;
	justify-content: center;
}
</style>
<style >
.flex {
	display: flex;
}

.flex-column {
	flex-direction: column;
}

.flex-row {
	flex-direction: row;
}

.justify-between {
	justify-content: space-between;
}

.justify-center {
	justify-content: center;
}

.items-center {
	align-items: center;
}
</style>

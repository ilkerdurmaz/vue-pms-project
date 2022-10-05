<script setup>
import Card from './components/Card/Card.vue';

</script>

<template>
	<div>
		<Card />
	</div>
</template>

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

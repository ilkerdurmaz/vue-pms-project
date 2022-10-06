<script setup>
const props = defineProps(["icon"]);
</script>

<template>
	<div>
		<span class="material-icons">{{ props.icon }}</span>
	</div>
</template>

<style lang="scss">
.material-icons {
	transition: 0.2s ease-out;
	cursor: pointer;
}
</style>

<script setup>

	const props = defineProps(["icon","color"])

</script>

<template>
	<div>
		<span class="material-icons">{{props.icon}}</span>
	</div>
</template>

<style lang="scss">
.material-icons {
		cursor: pointer;
			}
</style>
<script setup>
const props = defineProps(["image", "size"]);
</script>

<template>
	<img
		class="photo"
		:src="props.image"
		:width="props.size"
		:height="props.size"
	/>
</template>
<style lang="scss">
.photo {
	border-radius: 50%;
}
</style>

<script setup>
import Icon from "./icon.vue";

const props = defineProps(["title", "icon"]);
</script>

<template>
	<div class="sideBarItem">
		<Icon :icon="props.icon" />
		<span>{{ props.title }}</span>
	</div>
</template>

<style lang="scss" scoped>
.sideBarItem {
	display: flex;
	align-items: center;
	gap: 19px;

	cursor: pointer;
	 
}
 :hover  {
		background-color: #f9f9f9;
		color: #00db99;
	}
</style>

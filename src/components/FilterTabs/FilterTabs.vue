<script setup>
import Tab from "./Tab.vue";
import SortGroup from "./SortGroup.vue";
import { ref } from "vue";

const titles = ref([
	{
		name: "All",
		active: true,
	},
	{
		name: "Inactive",
		active: false,
	},
	{
		name: "Active",
		active: false,
	},
	{
		name: "On hold",
		active: false,
	},
	{
		name: "Completed",
		active: false,
	},
]);

function selectTab(value) {
	console.log(value + " tab selected.");
	titles.value = titles.value.map((item) =>
		item.name === value ? { ...item, active: true } : { ...item, active: false }
	);

	return;
}

function sortClick() {
	console.log("SortButton clicked");
	return;
}
</script>

<template>
	<div class="tabs-container">
		<div class="tabs-container--tabs">
			<Tab v-for="title in titles" :key="title.name" :title="title.name" :active="title.active"
				@click="selectTab(title.name)" />
		</div>
		<SortGroup @sortClick="sortClick" />
	</div>
</template>
<style lang="scss" scoped>
.tabs-container {
	display: flex;
	justify-content: space-between;
	box-sizing: border-box;
	border: 1px solid #f1f2f7;
	border-radius: 8px;
	height: 3.25rem;
	padding: 0 1.25rem;
	width: 100%;

	&--tabs {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 3rem;
		margin: 0 1.25rem;
	}
}
</style>

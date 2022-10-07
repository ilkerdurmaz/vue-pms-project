<script setup>
import Sidebar from "./components/SideBar/Sidebar.vue";
import Header from "./components/Header/Header.vue";
import CardContainer from "./components/Card/CardContainer.vue";
import { ref } from "vue";
import ProjectData from "./assets/data/ProjectData.json";
import { computed } from "@vue/reactivity";

const title = ref("Projects");

const selectedTab = ref("All");

function tabValueChanged(value) {
	selectedTab.value = value;
}

const filteredData = computed(() => {
	if (selectedTab.value == "All") return ProjectData;

	return ProjectData.filter((item) => item.status === selectedTab.value);
});

const setTitle = (value) => {
	title.value = value;
	return;
};
</script>

<template>
	<div class="main">
		<Sidebar @setTitle="setTitle" />
		<div class="main__content">
			<Header :title="title" @tabValue="tabValueChanged" />
			<CardContainer :data="filteredData" />
		</div>
	</div>
</template>

<style lang="scss">
.main {
	width: 100%;
	height: 100%;
	display: flex;

	&__content {
		border: 1px solid #f1f2f7;
		width: 100%;
		height: 100%;
	}
}
</style>

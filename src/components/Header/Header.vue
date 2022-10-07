<script setup>
import FilterTabs from "../FilterTabs/FilterTabs.vue";
import PlusButton from "./PlusButton.vue";
import SearchBar from "./SearchBar.vue";
import ProfileDetails from "./ProfileDetails.vue";
import Icon from "../Icons/Icon.vue";
import { ref } from "vue";

const props = defineProps(["title"]);

function searchTriggered(value) {
	console.log("Search value: " + value);
	return
}
function plusButtonClick() {
	console.log("PlusButton Clicked");
	return;
}

const icons = ref([
	{
		name: "comment",
	},
	{
		name: "notifications",
	},
	{
		name: "settings",
	},
]);

</script>

<template>
	<div class="header_container">
		<div class="header_top">
			<div>
				<h1 class="header_title">{{props.title}}</h1>
			</div>
			<SearchBar @search="searchTriggered" />
			<div class="header_top_right">
				<div class="icons_container">
					<Icon v-for="item in icons" :icon="item.name" />
				</div>
				<ProfileDetails />
			</div>
		</div>
		<div class="header_bottom">
			<PlusButton @btnClick="plusButtonClick" />
			<FilterTabs />
		</div>
	</div>
</template>

<style  lang="scss">
.header_container {
	display: flex;
	flex-direction: column;
	gap: 28px;
	padding: 32px 30px;
}

.header_bottom {
	display: flex;
	gap: 30px;
}
.header_top {
	display: flex;
	align-items: center;
	justify-content: space-between;
}
.header_title {
	margin: 0;
	width: 150px;
	font : {
		family: "Roboto";
		style: normal;
		weight: 500;
		size: 24px;
	}
	line-height: 28px;
	color: #3c557a;
}
.material-icons {
		color: #717986;
			}

.header_top_right {
	display: flex;
	justify-content: center;
	margin: 0px 3.5rem 0px 0px;
}
.icons_container {
	display: flex;
	align-items: center;
	gap: 2rem;
	div {
		height: 28px;
		width: 28px;
	}
}

</style>

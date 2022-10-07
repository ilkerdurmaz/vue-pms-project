<script setup>
import FilterTabs from "../FilterTabs/FilterTabs.vue";
import PlusButton from "./PlusButton.vue";
import SearchBar from "./SearchBar.vue";
import ProfileDetails from "./ProfileDetails.vue";
import Icon from "../Icons/Icon.vue";
import { ref } from "vue";

const props = defineProps(["title"]);
const emit = defineEmits(["tabValue"]);

function filterTab(value) {
	emit("tabValue", value);
}

function searchTriggered(value) {
	console.log("Search value: " + value);
	return;
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
	<div class="header">
		<div class="header--top">
			<div>
				<h1 class="top--title">{{ props.title }}</h1>
			</div>
			<SearchBar @search="searchTriggered" />
			<div class="top--right">
				<div class="right--icons">
					<Icon v-for="item in icons" :icon="item.name" />
				</div>
				<ProfileDetails />
			</div>
		</div>
		<div class="header--bottom">
			<PlusButton @btnClick="plusButtonClick" />
			<FilterTabs @selectedTab="filterTab" />
		</div>
	</div>
</template>

<style lang="scss">
.header {
	display: flex;
	flex-direction: column;
	gap: 28px;
	padding: 32px 30px;

	&--top {
		display: flex;
		align-items: center;
		justify-content: space-between;

		.top--title {
			margin: 0;
			width: 150px;
			line-height: 28px;
			color: #3c557a;

			font : {
				family: "Roboto";
				style: normal;
				weight: 500;
				size: 24px;
			}
		}

		.top--right {
			display: flex;
			justify-content: center;
			margin: 0px 3.5rem 0px 0px;

			.right--icons {
				display: flex;
				align-items: center;
				gap: 2rem;
			}
		}
	}

	&--bottom {
		display: flex;
		gap: 30px;
	}
}

.material-icons {
	color: #717986;
}
</style>

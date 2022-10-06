<script setup>
import FilterTabs from "../FilterTabs/FilterTabs.vue";
import PlusButton from "./PlusButton.vue";
import SearchBar from "./SearchBar.vue";
import ProfileDetails from "./ProfileDetails.vue";
function plusButtonClick() {
	console.log("clicked");
}
</script>

<template>
	<div class="header_container">
		<div class="header_top">
			<div>
				<h1 class="header_title">Projects</h1>
			</div>
			<SearchBar />
			<div class="header_top_right">
				<div class="icons_container">
					<div class="iconumsu"></div>
					<div class="iconumsu"></div>
					<div class="iconumsu"></div>
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

<style scoped lang="scss">
.header_container {
	display: flex;
	flex-direction: column;
	gap: 28px;
	border: 1px solid grey;
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
	font : {
		family: "Roboto";
		style: normal;
		weight: 500;
		size: 24px;
	}
	line-height: 28px;
	color: #3c557a;
}

.header_top_right {
	display: flex;
	justify-content: center;
}

.icons_container {
	display: flex;
	align-items: center;
	gap: 2rem;
	div {
		height: 28px;
		width: 28px;
		background-color: red;
	}
}
</style>

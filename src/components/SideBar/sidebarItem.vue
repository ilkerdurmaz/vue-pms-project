<script setup>
import Icons from "../Icons/Icons.vue";

const props = defineProps(["icon","title"]);

const logOut = () => {
		return props.title === "LogOut" ? true : false;
	}

</script>

<template>
	<div class="sidebarItem" :class="{'logOut' : logOut()}">
		<Icons :icon="props.icon" />
		<span class="sidebarItem__text">{{ props.title }}</span>
	</div>
</template>

<style lang="scss">

.sidebarItem {
		display: flex;
		align-items: center;
		text-decoration: none;
		transition: 0.2s ease-out;
		border-radius: 8px;
		margin: 0px 20px 5px 20px;
		padding: 16px 0 17px 30px;
		cursor: pointer;
		color: #717986;

		&__text {
			font-weight: 400;
			font-size: 16px;
			line-height: 19px;
			color: #717986;
			margin-left: 18.5px;
			transition: 0.2s ease-out;
		}
		&:hover {
			background-color: #F9F9F9;
			color: #00DB99;
				.sidebarItem__text{
				color: #00DB99;
			}
		}
	&.logOut{
		.material-icons {
			color: #FF285C;
		}
		.sidebarItem__text {
			color: #FF285C;
		}
		&:hover {
			background-color: #fff;
			}
		}}
</style>

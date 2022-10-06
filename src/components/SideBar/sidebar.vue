<script setup>
import { ref } from "vue";
import SidebarItem from "./sidebarItem.vue";
import Logo from "../../assets/svg/SideBarSvg/Logo.vue";
import LogOut from "../../assets/svg/SideBarSvg/LogOut.vue";

const items = ref([
	{
		icon: "home",
		title: "Dashboard",
	},
	{
		icon: "grid_view",
		title: "Projects",
	},
	{
		icon: "schema",
		title: "Modules",
	},
	{
		icon: "send",
		title: "Sprint",
	},
	{
		icon: "group",
		title: "Members",
	},
	{
		icon: "browser_updated",
		title: "Reports",
	},
]);

const clickHandler = (value) => {
	console.log(value);
};

const is_expanded = ref(false);

const ToggleMenu = () => {
	is_expanded.value = !is_expanded.value;
};
</script>

<template>
	<aside :class="`${is_expanded && 'is-expanded'}`">
		<div class="menu-toggle-wrap">
			<button class="menu-toggle" @click="ToggleMenu">
				<span class="material-icons">menu_open</span>
			</button>
		</div>
		<div class="logo">
			<Logo></Logo>
		</div>

		<div class="menu">
			<SidebarItem
				v-for="item in items"
				:icon="item.icon"
				:title="item.title"
				@click="clickHandler(item.title)"
			>
			</SidebarItem>
		</div>

		<div class="flex"></div>

		<div class="logOut">
			<LogOut></LogOut>
		</div>
	</aside>
</template>

<style lang="scss" scoped>
aside {
	display: flex;
	flex-direction: column;
	width: calc(1rem + 37px);
	min-height: 100vh;
	overflow: hidden;
	padding: 1rem;

	background-color: var(--light);
	color: var(--dark-alt);

	transition: 0.2s ease-out;

	.flex {
		flex: 1 1 0;
	}

	.logOut {
		margin-bottom: 2rem;
	}

	.menu-toggle-wrap {
		display: flex;
		justify-content: flex-end;
		margin-bottom: 1rem;

		position: relative;
		top: 0;
		transition: 0.2s ease-out;

		.menu-toggle {
			transition: 0.2s ease-out;

			.material-icons {
				font-size: 1.5rem;
				color: var(--dark-alt);
			}
		}
	}

	.menu {
		margin: 1rem;
		display: flex;
		flex-direction: column;
		gap: 38px;
	}

	&.is-expanded {
		width: var(--sidebar-width);

		.menu-toggle-wrap {
			top: 1rem;
			.menu-toggle {
				transform: rotate(0deg);
			}
		}
	}

	@media (max-widht: 768px) {
		position: fixed;
		z-index: 99;
	}
}
</style>

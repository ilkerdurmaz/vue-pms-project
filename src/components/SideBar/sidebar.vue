<script setup>
import { ref } from "vue";
import SidebarItem from "./sidebarItem.vue";
import SideBarData from "../..//assets/data/SidebarData.json";
import Logo from "./Logo.vue";
import Icon from "../Icons/Icon.vue";

const iconData = ref(SideBarData);
const is_expanded = ref(false);

const emits = defineEmits(["setTitle"])

const clickHandler = (title) => {
	emits("setTitle", title)
};

const isActive = (id) => {
	iconData.value.map((item) => {
		return item.id === id ? (item.active = true) : (item.active = false);
	});
}

const ToggleMenu = () => {
	return is_expanded.value = !is_expanded.value;
};

</script>

<template>

	<div class="sidebar">
		<aside class="aside" :class="`${is_expanded && 'is-expanded'}`">
			<div class="aside__header">
				<Logo />
				<div class="menu-toggle-wrap">
					<button class="menu-toggle" @click="ToggleMenu">
						<Icon icon="menu_open" />
					</button>
				</div>
			</div>
			<div class="aside__content">
				<SidebarItem v-for="item in iconData" :key="item.id" :icon="item.name" :title="item.text" :id="item.id"
					:active="item.active" @click="clickHandler(item.text)" @setID="isActive">
				</SidebarItem>
			</div>
			<div class="aside__footer">
				<SidebarItem :icon="'logout'" :title="'LogOut'" />
			</div>
		</aside>
	</div>
</template>

<style lang="scss" >
.sidebar {
	display: flex;
	flex-direction: column;
	min-height: 100vh;
	height: 100vh;

}

.aside {
	display: flex;
	flex-direction: column;
	width: 315px;
	min-height: 100vh;
	overflow: hidden;
	transition: 0.2s ease-out;
	border-right: 1px solid #F1F2F7;
	position: relative;

	&__header {
		display: flex;
		align-items: center;
		width: 100%;
		position: relative;
		padding: 44px 18px 0px 40px;
	}

	.menu-toggle-wrap {
		position: absolute;
		right: 21.67px;
		transition: 0.2s ease-out;

		.menu-toggle {
			.material-icons {
				font-size: 1.5rem;
				color: #717986;
			}

			&:hover {
				.material-icons {
					color: #717986;

				}
			}
		}
	}

	&__content {
		width: 315px;
		height: 90vh;
		padding: 47px 0 0 0;
		display: flex;
		flex-direction: column;
		position: relative;

	}

	&__footer {
		width: 315px;
		border-top: 1px solid #F1F2F7;
		position: fixed;
		bottom: 5px;
		height: 150px;
		padding-top: 20px;
		background-color: #ffffff;

	}

	&.is-expanded {
		width: 80px;

		.header {
			visibility: hidden;
		}

		.menu-toggle-wrap {
			left: 38px;
		}

		.aside__footer {
			width: 80px;
			position: relative;
			bottom: 0;
		}

		.sidebarItem {
			width: 50px;
			padding: 16px 0 17px 13px;

			&__text {
				opacity: 6;
			}
		}

		.material-icons {
			margin-right: 1rem;
		}
	}
}
</style>

<script setup>
	import { ref } from "vue";
	
	const is_expanded = ref(localStorage.getItem("is_expanded") === "true");
	
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
				<img src="../assets/svg/logo.svg" alt="Vue" />
			</div>
	
			<div class="menu">
				<router-link class="button">
					<span class="material-icons">home</span>
					<span class="text">Dashboard</span>
				</router-link>
				<router-link class="button">
					<span class="material-icons">grid_view</span>
					<span class="text">Projects</span>
				</router-link>
				<router-link class="button">
					<span class="material-icons">schema</span>
					<span class="text">Modules</span>
				</router-link>
				<router-link class="button">
					<span class="material-icons">send</span>
					<span class="text">Sprint</span>
				</router-link>
				<router-link class="button">
					<span class="material-icons">group</span>
					<span class="text">Members</span>
				</router-link>
				<router-link class="button">
					<span class="material-icons">browser_updated</span>
					<span class="text">Reports</span>
				</router-link>
			</div>
	
			<div class="flex"></div>
			<div class="menu">
				<router-link class="button">
					<span class="material-icons">logout</span>
					<span class="text">LogOut</span>
				</router-link>
			</div>
		</aside>
	</template>
	
	<style lang="scss" scoped>
	aside {
		display: flex;
		flex-direction: column;
		width: calc(1rem + 32px);
		min-height: 100vh;
		overflow: hidden;
		padding: 1rem;
	
		background-color: var(--light);
		color: var(--dark-alt);
	
		transition: 0.2s ease-out;
	
		.flex {
			flex: 1 1 0;
		}
	
		.logo {
			margin-bottom: 2rem;
	
			img {
				width: 7rem;
			}
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
	
				&:hover {
					.material-icons {
						color: var(--primary);
						transform: translateX(0.5rem);
					}
				}
			}
		}
	
		.button .text {
			opacity: 0;
			transition: 0.3s ease-out;
		}
		.menu {
			margin: 0 -1rem;
	
			.button {
				display: flex;
				align-items: center;
				text-decoration: none;
	
				padding: 0.5rem 1rem;
				transition: 0.2s ease-out;
	
				.material-icons {
					font-size: 1.5rem;
					color: var(--dark);
					transition: 0.2s ease-out;
				}
	
				.text {
					color: var(--dark);
					transition: 0.2s ease-out;
				}
	
				&:hover {
					background-color: var(--dark-alt);
	
					.material-icons .text {
						color: var(--primary);
					}
				}
			}
		}
	
		&.is-expanded {
			width: var(--sidebar-width);
	
			.menu-toggle-wrap {
				top: 0rem;
				.menu-toggle {
					transform: rotate(0deg);
				}
			}
	
			.button,
			.text {
				opacity: 6;
			}
	
			.button {
				.material-icons {
					margin-right: 1rem;
				}
			}
		}
	
		@media (max-widht: 768px) {
			position: fixed;
			z-index: 99;
		}
	}
	</style>
	
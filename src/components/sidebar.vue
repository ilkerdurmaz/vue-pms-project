<script setup>
	import { ref } from "vue";
	
	const is_expanded = ref(false);

	const ToggleMenu = () => {
		is_expanded.value = !is_expanded.value;
	};
	console.log(is_expanded.value);
	</script>
	
	<template>
		<aside :class="`${is_expanded && 'is-expanded'}`">
			
			<div class="logo">
				<div class="logo__content">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
					<circle cx="12" cy="12" r="10" stroke="#0075FF" stroke-width="4"/>
					</svg>
					<h1 class="logo__text" >ChirKuut</h1>
			</div>

					<div class="menu-toggle-wrap">
						<button class="menu-toggle" @click="ToggleMenu">
							<span class="material-icons">menu_open</span>
						</button>
					</div>
			</div>
	
			<div class="menu">
				<div class="button">
					<span class="material-icons">home</span>
					<span class="text">Dashboard</span>
				</div>
				<div class="button">
					<span class="material-icons">grid_view</span>
					<span class="text">Projects</span>
				</div>
				<div class="button">
					<span class="material-icons">schema</span>
					<span class="text">Modules</span>
				</div>
				<div class="button">
					<span class="material-icons">send</span>
					<span class="text">Sprint</span>
				</div>
				<div class="button">
					<span class="material-icons">group</span>
					<span class="text">Members</span>
				</div>
				<div class="button">
					<span class="material-icons">browser_updated</span>
					<span class="text">Reports</span>
				</div>
				
				<div class="logOut">
					<span class="material-icons">logout</span>
					<span class="text">LogOut</span>
				</div>


			</div>
	

		</aside>
	</template>
	
	<style lang="scss" scoped>
	aside {
		display: flex;
		flex-direction: column;
		width:315px;
		min-height: 100vh;
		overflow: hidden;
		// background-color: var(--light);
		color: #717986;
		transition: 0.2s ease-out;
		border-right: 1px solid #e5e5e5;
	
		.logo {
			display: flex;
			align-items: center;
			height: 50px;
			width: 315px;
			position: relative;
			padding: 44px 18px 0px 40px;

			&__content{
				width:100%;
				display: flex;
				align-items: center;

			}
			&__text{
				font-style: normal;
				font-weight: 700;
				font-size: 20px;
				line-height: 23px;
				margin-left: 10px;
				color: black;
				}

			img {
				width: 7rem;
			}
		}

		.menu-toggle-wrap {
			position: absolute;
			right: 10px;
			transition: 0.2s ease-out;
			.menu-toggle {
				transition: 0.2s ease-out;
	
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
	
		.button .text {
			opacity: 1;
			transition: 0.3s ease-out;
		}
		.menu {
			margin: 47px 0 0 0;
			position: relative;
	
			.button {
				display: flex;
				align-items: center;
				text-decoration: none;
				transition: 0.2s ease-out;
				border-radius: 8px;
				margin: 0px 20px 5px 20px;
				padding: 16px 0 17px 0;
				cursor: pointer;
				
				.material-icons {
					padding-left: 29.67px;
					color: #717986;
					transition: 0.2s ease-out;
				}
	
				.text {
					font-style: normal;
					font-weight: 400;
					font-size: 16px;
					line-height: 19px;
					color: #717986;
					margin-left: 18.5px;
					transition: 0.2s ease-out;
				}
	
				&:hover {
					background-color: #F9F9F9;
	
					.material-icons  {
						color: #00DB99;
					}

					.text {
						color: #00DB99;
					}

				}
			}
		}
	
		&.is-expanded {
			width: 80px;
			.logo__content {
				visibility: hidden;
			}
			.menu-toggle-wrap {
				left: 55px;
				.menu-toggle {
					// transform: rotate(0deg);
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
	
	}
	</style>
	
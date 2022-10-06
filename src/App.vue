<script setup>
	import Sidebar from './components/SideBar/sidebar.vue'
	
	</script>
	
	<template>
			<div class="app">
				 <Sidebar />
			</div>
	</template>
	
	<style lang="scss">
	:root {
	--primary: #00db99;
		--primary-alt: #00db99;
		--dark: #717986;
		--dark-alt: #969696;
		--light: #ffffff;
		--red: #FF285C;
		--sidebar-width: 200px;
	}
	
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: 'Roboto', sans-serif;
	}
	
	body {
		background: var(--light);
	}
	
	button {
		cursor: pointer;
		appearance: none;
		border: none;
		background: none;
	}
	
	.app {
		display: flex;
	
		main {
			flex: 1 1 0;
			padding: 2rem;
	
			@media (max-width: 768px) {
				padding-left: 6rem;
				
			}
		}
	}
	</style>
	
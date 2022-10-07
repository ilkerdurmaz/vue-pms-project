<script setup>
	import Sidebar from './components/SideBar/sidebar.vue'
	import Header from './components/Header/Header.vue';
	import Card from "./components/Card/Card.vue";
</script>
	
	<template>
			<div class="main">
				 <Sidebar />
				<div class="main__content">
					<Header/>
					<Card/>
				</div>
			</div>
	</template>


<style lang="scss" >
	
	.main{
    width: 100%;
    height: 100%;
    display: flex;
		
		&__content{
			width: 100%;
			height: 100%;
		}
	}
   

	</style>

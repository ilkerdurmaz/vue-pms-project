<script setup>
	import Sidebar from './components/SideBar/Sidebar.vue'
	import Header from './components/Header/Header.vue';
	import Card from "./components/Card/Card.vue";
	import { ref } from 'vue';

	const title = ref("Projects");

	const setTitle = (value) => {
		title.value = value;
		return
	};

</script>
	
	<template>
			<div class="main">
				 <Sidebar @setTitle="setTitle" />
				<div class="main__content">
					<Header :title="title" />
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

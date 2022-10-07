<script setup>

	const props = defineProps(["icon","color"])

	const isNotification = () => {
		return props.icon === "notifications" ? true : false;
	}
</script>

<template>
	<div class="icon" >
		<span class="material-icons">{{props.icon}}</span>
		<span v-if="isNotification()" class="notifications"></span>
	</div>
</template>

<style lang="scss">
.icon{
	position: relative;
	.material-icons {
			cursor: pointer;
				}
	.notifications{
		width: 8px;
		height: 8px;
		background: #FF285C;
		border-radius: 50%;
		position: absolute;
		top: 2px;
		right: 5px;
	}
}

</style>
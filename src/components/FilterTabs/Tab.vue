<script setup>
defineProps({
	title: {
		type: String,
		default: "Title",
	},
	active: {
		type: Boolean,
		default: false,
	},
});
</script>

<template>
	<div class="tab" :class="{ active }">
		<span class="dot" v-if="active"></span>
		{{ title }}
	</div>
</template>

<style scoped>
.tab {
	display: flex;
	flex-direction: column;
	align-items: center;
	font-style: normal;
	font-weight: 400;
	font-size: 14px;
	line-height: 16px;
	color: #8b8b8b;
	margin: auto 0 1.125rem 0;
	cursor: pointer;
}
.tab:hover {
	color: #25364f;
}
.dot {
	width: 4px;
	height: 4px;
	background: #3c557a;
	border-radius: 50%;
	margin-bottom: 2px;
}
.active {
	font-weight: 700;
	color: #25364f;
}
</style>

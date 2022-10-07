<script setup>
	const props = defineProps(["task","users"]);
</script>

<template>
	<div class="counter">
		<div class="counter--item">
			<span>{{ props.task }}</span>
			<span>Tasks</span>
		</div>
		<div class="line"></div>
		<div class="counter--item">
			<span>{{ props.users }}</span>
			<span>Users</span>
		</div>
	</div>
</template>

<style lang="scss">
.counter {
	display: flex;
	justify-content: space-around;
	align-items: center;
	background: #f9f9f9;
	border-radius: 7px;
	width: fit-content;
	width: 148px;
	height: 70px;

	&--item {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 4px;
		width: 52px;

		:first-child {
			font-weight: 700;
			font-size: 18px;
			line-height: 21px;
			color: #3c557a;
			letter-spacing: 1px;
		}

		:last-child {
			font-weight: 400;
			font-size: 12px;
			line-height: 14px;
			color: #717986;
		}
	}
}
.line {
	height: 42px;
	width: 1px;
	background: #cddcee;
}
</style>

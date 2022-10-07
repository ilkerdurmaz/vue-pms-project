<script setup>
const props = defineProps(["value"])
</script>
<template>
	<div class="progress">
		<div class="progress--head flex justify-between">
			<p class="progress--title">Progress</p>
			<p class="progress--value">{{ value }}</p>
		</div>
		<progress id="file" :value="value" max="100"> {{ value }} </progress>
	</div>
</template>
<style lang="scss">
.progress {
	width: 100%;

	&--head {
		color: #717986;
	}

	&--title {
		font-size: 15px;
		line-height: 15.23px;
		font-weight: 500;
	}

	&--value {
		font-size: 12px;
		line-height: 14.06px;
		font-weight: 400;
		color: #3C557A;
	}

}
progress {
	border-radius: 7px;
	width: 100%;
	height: 8px;
}

progress::-webkit-progress-bar {
	background-color: #F1F2F7;
	border-radius: 75px;
}

progress::-webkit-progress-value {
	background-color: #1BE3A7;
	border-radius: 75px;
}
</style>
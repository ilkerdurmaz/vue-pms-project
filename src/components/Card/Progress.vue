<script setup>
const props = defineProps(["value", "status"]);
</script>
<template>
	<div class="progress">
		<div class="progress--head flex justify-between">
			<p class="progress--title">Progress</p>
			<p class="progress--value">{{ value }}</p>
		</div>
		<progress :class="props.status" id="file" :value="value" max="100">
			{{ value }}
		</progress>
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
		color: #3c557a;
	}
}
progress {
	border-radius: 7px;
	width: 100%;
	height: 8px;
}

progress {
	&::-webkit-progress-bar {
		background-color: #f1f2f7;
		border-radius: 75px;
	}
	&::-moz-progress-bar {
		background-color: #f1f2f7;
		border-radius: 75px;
	}
}

progress {
	&.Active {
		&::-webkit-progress-value {
			background-color: #00db99;
			border-radius: 75px;
		}
		&::-moz-progress-bar {
			background-color: #00db99;
			border-radius: 75px;
		}
	}

	&.OnHold {
		&::-webkit-progress-value {
			background-color: #f0bb00;
			border-radius: 75px;
		}
		&::-moz-progress-bar {
			background-color: #f0bb00;
			border-radius: 75px;
		}
	}

	&.Inactive {
		&::-webkit-progress-value {
			background-color: #ff285c;
			border-radius: 75px;
		}
		&::-moz-progress-bar {
			background-color: #ff285c;
			border-radius: 75px;
		}
	}

	&.Completed {
		&::-webkit-progress-value {
			background-color: #0066b2;
			border-radius: 75px;
		}
		&::-moz-progress-bar {
			background-color: #0066b2;
			border-radius: 75px;
		}
	}
}
</style>

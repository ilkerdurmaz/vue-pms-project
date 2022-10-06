<script setup>
const props = defineProps(["status"]);
</script>
<template>
	<div class="status">
		<span :class="props.status" class="disc"></span>
		<p :class="props.status">{{ props.status }}</p>
	</div>
</template>
<style lang="scss">
.status {
	display: flex;
	align-items: center;
	gap: 8px;
	span {
		.Active {
			background: #00db99;
		}
		.OnHold {
			background: #f0bb00;
		}
		.Inactive {
			background: #ff285c;
		}
	}
	p {
		.Active {
			color: #00db99;
		}
		.OnHold {
			color: #f0bb00;
		}
		.Inactive {
			color: #ff285c;
		}
	}
}
.disc {
	display: block;
	width: 8px;
	height: 8px;
	border-radius: 50%;
}
</style>

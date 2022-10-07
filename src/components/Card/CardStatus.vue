<script setup>
	const props = defineProps(["status"]);
</script>

<template>
	<div class="status">
		<span :class="'disc--' + props.status" class="disc"></span>
		<p :class="'status--' + props.status">{{ props.status }}</p>
	</div>
</template>

<style lang="scss">
.disc {
	display: block;
	width: 8px;
	height: 8px;
	border-radius: 50%;

	&--Active {
		background: #00db99;
	}
	&--OnHold {
		background: #f0bb00;
	}
	&--Inactive {
		background: #ff285c;
	}
	&--Completed {
		background: #0066b2;
	}
}
.status {
	display: flex;
	align-items: center;
	gap: 8px;
	font-weight: 500;
	font-size: 13px;
	line-height: 15px;

	&--Active {
		color: #00db99;
	}
	&--OnHold {
		color: #f0bb00;
	}
	&--Inactive {
		color: #ff285c;
	}
	&--Completed {
		color: #0066b2;
	}
}
</style>

<script setup>
defineProps({
	name: {
		type: String,
		default: "New",
	},
});
const emit = defineEmits(["btnClick"]);
</script>

<template>
	<div>
		<button class="btn" @click="emit('btnClick')">
			<svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
				<path
					d="M15 7H8.99998V1C8.99998 0.734783 8.89463 0.48043 8.70709 0.292893C8.51955 0.105357 8.2652 0 7.99998 0C7.73477 0 7.48041 0.105357 7.29288 0.292893C7.10534 0.48043 6.99998 0.734783 6.99998 1V7H0.999984C0.734767 7 0.480414 7.10536 0.292877 7.29289C0.105341 7.48043 -1.62125e-05 7.73478 -1.62125e-05 8C-1.62125e-05 8.26522 0.105341 8.51957 0.292877 8.70711C0.480414 8.89464 0.734767 9 0.999984 9H6.99998V15C6.99998 15.2652 7.10534 15.5196 7.29288 15.7071C7.48041 15.8946 7.73477 16 7.99998 16C8.2652 16 8.51955 15.8946 8.70709 15.7071C8.89463 15.5196 8.99998 15.2652 8.99998 15V9H15C15.2652 9 15.5196 8.89464 15.7071 8.70711C15.8946 8.51957 16 8.26522 16 8C16 7.73478 15.8946 7.48043 15.7071 7.29289C15.5196 7.10536 15.2652 7 15 7Z"
					fill="white" />
			</svg>
			{{ name }}
		</button>
	</div>
</template>

<style lang="scss" scoped>
.btn {
	display: flex;
	align-items: center;
	justify-content: center;
	height: 3.25rem;
	width: 127px;
	gap: 11px;
	background: #00db99;
	border-radius: 26px;
	color: white;
	font-weight: 500;
	font-size: 18px;
	line-height: 21px;
}
</style>

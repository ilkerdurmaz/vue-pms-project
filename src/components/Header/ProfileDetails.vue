<script setup>
defineProps({
	name: {
		type: String,
		default: "Tolga Eğilmezel",
	},
	mail: {
		type: String,
		default: "tolga.egilmezel@gmail.com",
	},
	imgSrc: {
		type: String,
		default:
			"https://media-exp1.licdn.com/dms/image/C5603AQGzQpv7w1G4eA/profile-displayphoto-shrink_200_200/0/1517785162616?e=2147483647&v=beta&t=MyO0L5FN0NNYzo0yGW3lvP3GIuehvTxemFBzzYB555U",
	},
});
</script>
<template>
	<div class="profile_details">
		<img :src="imgSrc" />
		<div class="name_group">
			<h4>{{ name }}</h4>
			<p>{{ mail }}</p>
		</div>
	</div>
</template>
<style lang="scss" scoped>
.profile_details {
	display: flex;
	align-items: center;
	gap: 1rem;
	margin: 0 0 0 3.25rem;
	img {
		border-radius: 50%;
		width: 40px;
	}
}
.name_group {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
	gap: 4px;
	h4 {
		margin: 0;
		font-weight: 500;
		font-size: 16px;
		line-height: 19px;
		color: #25364f;
	}
	p {
		margin: 0;
		font-weight: 400;
		font-size: 12px;
		line-height: 14px;
		color: #8b8b8b;
	}
}
</style>

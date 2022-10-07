<template>
	<div class="logo">
		<div class="logo--svg">
			<svg
				width="24"
				height="24"
				viewBox="0 0 24 24"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<circle cx="12" cy="12" r="10" stroke="#0075FF" stroke-width="4" />
			</svg>
			<svg
				class="logo--circle"
				width="16"
				height="16"
				viewBox="0 0 16 16"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<circle cx="8" cy="8" r="6" stroke="#1BE3A7" stroke-width="4" />
			</svg>
		</div>
		<h1 class="logo--text">ChirKuut</h1>
	</div>
</template>

<style lang="scss" scoped>
.logo {
	width: 100%;
	display: flex;
	align-items: center;
	padding-left: 8px;

	&--svg {
		margin-right: 18px;
		position: relative;
	}

	&--circle {
		position: absolute;
		top: 15px;
		left: 15px;
	}

	&--text {
		font-style: normal;
		font-weight: 700;
		font-size: 20px;
		line-height: 23px;
		margin-left: 10px;
		color: black;
	}
}
</style>

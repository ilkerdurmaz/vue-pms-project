<script setup>
import Progress from '../Progress.vue';
import CardCounter from './CardCounter.vue'

</script>
<template>
	<div class="card flex justify-between flex-column">
		<div class="card--head flex flex-column">
			<div class="flex flex-row justify-between">
				<p class="head--title">
					Project Title goes here
				</p>
				<div class="head--icon">
					<span class="material-symbols-outlined">
						edit
					</span>
					<span class="material-symbols-outlined">
						more_vert
					</span>
				</div>
			</div>
			<div style="font-size:13px; color: #00DB99;">
				status gelecek
			</div>
		</div>
		<div class="card--body flex flex-row justify-between items-center">
			<div class="body--date flex flex-column">
				<p class="date--text">Start date</p>
				<p class="date--format">12 Sep 2021</p>
			</div>
			<div class="body--status">
				<p class="status--text">Status</p>
				<p style="font-size:13px; color: #00DB99;">status gelecek</p>
			</div>
			<div class="body--info" >
				<div class="counter-group">
					<CardCounter :data="{number : 24, name : 'Task'}"></CardCounter>
					<CardCounter :data="{number : 1, name : 'Members'}"></CardCounter>
				</div>
			</div>
		</div>
		<div class="members" style="height:60px; background-color:gray;">
			<p>safsa</p>
			<p>safsa</p>
		</div>
		<div class="card-footer">
			<Progress></Progress>

		</div>

	</div>

</template>
<style lang="scss">
.card {
	box-sizing: border-box;
	width: 495px;
	height: 300px;
	padding: 24px;
	background: #FFFFFF;
	border: 1px solid #E5E5E5;
	border-radius: 8px;
	margin: 25px;

	&:hover {
		box-shadow: 0px 3px 36px 12px #507EA91F;


	}


	&--head {
		color: #8B8B8B;

		.head--title {
			color: #3C557A;
			font-weight: 500;
			font-size: 18px;
			line-height: 21.09px;
			gap: 16px;
		}

		.head--icon {
			:not(:last-child) {
				margin-right: 12px;
			}
		}
	}

	&--body {
		height: 73px;

		.body--date {
			color: #717986;
			font-size: 13px;
			line-height: 15.23px;
			font-weight: 500;

			.date--text {
				font-size: 12px;
				line-height: 14.06px;
				font-weight: 400;
			}

			.date--format {
				font-weight: 500;
				font-size: 13px;
				line-height: 15.23px;
			}
		}

		.body--status {
			margin-top: 15px;

			.status--text {
				color: #717986;
				font-size: 12px;
				line-height: 14.06px;
				font-weight: 400;
			}
		}
	}

	&--footer {}
}
</style>
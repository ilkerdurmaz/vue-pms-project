<script setup>
import Progress from "./Progress.vue";
import CardCounter from "./CardCounter.vue";
import Photo from "./Photo.vue";
import AddPhoto from "./AddPhoto.vue";
import CardStatus from "./CardStatus.vue";

const images = [
	"https://raw.githubusercontent.com/Front-End-Bootcamp/vue-dashboard-team-earth-1/develop/src/assets/img/abdullah.jpg",
	"https://user-images.githubusercontent.com/72731296/194396349-84056f61-5e01-48af-9516-1cd88e90d5bb.png",
	"https://raw.githubusercontent.com/Front-End-Bootcamp/vue-dashboard-team-earth-1/develop/src/assets/img/esra.jpg",
	"https://raw.githubusercontent.com/Front-End-Bootcamp/vue-dashboard-team-earth-1/develop/src/assets/img/fatih.jpg",
	"https://raw.githubusercontent.com/Front-End-Bootcamp/vue-dashboard-team-earth-1/develop/src/assets/img/ilker.jpg",
	"https://raw.githubusercontent.com/Front-End-Bootcamp/vue-dashboard-team-earth-1/develop/src/assets/img/irina.jpg",
];

const addUser = () => {
	console.log("Add Photo");
};
</script>
<template>
	<div class="card flex justify-between flex-column">
		<div class="card--head flex flex-column">
			<div class="flex flex-row justify-between">
				<p class="head--title">Project Title goes here</p>
				<div class="head--icon">
					<span class="material-symbols-outlined"> edit </span>
					<span class="material-symbols-outlined"> more_vert </span>
				</div>
			</div>
			
		</div>
		<div class="card--body flex flex-row justify-between items-center">
			<div class="body--date flex flex-column">
				<p class="date--text">Start date</p>
				<p class="date--format">12 Sep 2021</p>
			</div>
			<div class="body--status">
				<p class="status--text">Status</p>
				<CardStatus status="Active"></CardStatus>
			</div>
			<div class="body--info">
				<div class="counter-group">
					<CardCounter :data="[14, 4]"></CardCounter>
				</div>
			</div>
		</div>
		<div class="members">
			<p class="members--text">Members</p>
			<div class="photos">
				<Photo v-for="img in images" :key="img" :image="img" size="32"></Photo>
				<AddPhoto @setUser="addUser"></AddPhoto>
			</div>
		</div>
		<div class="card-footer">
			<Progress></Progress>
		</div>
	</div>
</template>

<style lang="scss">
.card {
	box-sizing: border-box;
	height: 300px;
	padding: 24px;
	background: #ffffff;
	border: 1px solid #e5e5e5;
	border-radius: 8px;
	margin: 0px 20px 30px 0px;

	&:hover {
		box-shadow: 0px 3px 36px 12px #507ea91f;
	}

	&--head {
		color: #8b8b8b;

		.head--title {
			color: #3c557a;
			font-weight: 500;
			font-size: 18px;
			line-height: 21.09px;
			gap: 16px;
		}

		.head--icon {
			:not(:last-child) {
				margin-right: 12px;
			}

			&>span {
				cursor: pointer;
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
				margin-bottom: 8px;
			}

			.date--format {
				font-weight: 500;
				font-size: 13px;
				line-height: 15.23px;
			}
		}

		.body--status {
			.status--text {
				color: #717986;
				font-size: 12px;
				line-height: 14.06px;
				font-weight: 400;
				margin-bottom: 8px;
			}
		}
	}
	.members--text {
		font-weight: 500;
		font-size: 13px;
		line-height: 15px;
		color: #717986;
		padding-bottom: 12px;
	}
	.photos {
		display: flex;
		gap: 4px;
	}
}
</style>

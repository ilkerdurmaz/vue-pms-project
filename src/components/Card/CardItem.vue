<script setup>
	import { ref } from "vue";
import Progress from "./Progress.vue";
import CardCounter from "./CardCounter.vue";
import Photo from "./Photo.vue";
import AddPhoto from "./AddPhoto.vue";
import CardStatus from "./CardStatus.vue";
import Icon from "../Icons/Icon.vue";

const addUser = () => {
	console.log("Add Photo");
};

const props = defineProps(["data"])

const progress = ref(props.data.progress);
const task = ref(props.data.tasks);
const users = ref(props.data.members);
const status = ref(props.data.status);
const images = ref(props.data.image);

console.log(props.data)

</script>
<template>
	<div class="card flex justify-between flex-column">
		<div class="card--head flex flex-column">
			<div class="flex flex-row justify-between">
				<p class="head--title">{{props.data.title}}</p>
				<div class="head--icon">
					<Icon icon="edit" />
					<Icon icon="more_vert " />
				</div>
			</div>
			
		</div>
		<div class="card--body flex flex-row justify-between items-center">
			<div class="body--date flex flex-column">
				<p class="date--text">Start date</p>
				<p class="date--format">{{props.data.date}}</p>
			</div>
			<div class="body--status">
				<p class="status--text">Status</p>
				<CardStatus :status="status"></CardStatus>
			</div>
			<div class="body--info">
				<div class="counter-group">
					<CardCounter :task="task" :users="users" ></CardCounter>
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
			<Progress :value="progress" ></Progress>
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
			display: flex;
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

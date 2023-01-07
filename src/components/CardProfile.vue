<template>
	<section class="profile">
		<div class="profile__header">
			<div class="profile__header-avatar">
				<img src="@/img/image-jeremy.png" alt="img-avatar" />
			</div>
			<p class="profile__header-name">
				<span class="note">Report for</span>
				<br />
				Jeremy Robson
			</p>
		</div>
		<div class="profile__timeframes">
			<a
				v-for="(timeFrame, index) of timeFrames"
				href="#"
				:key="index"
				class="profile__timeframes-link"
				:class="{ active: index == selectedItem }"
				@click="changeTimeFrame(timeFrame.value, index)"
				>{{ timeFrame.name }}</a
			>
		</div>
	</section>
</template>

<script>
import { ref, onMounted } from "vue";
export default {
	methods: {
		changeTimeFrame(value, index) {
			this.selectedItem = index; //переключаем класс active по индексу
      this.$emit('onChangeTimeFrame', value) //передаем текущее время во враппер
		}
	},
	setup() {
		const timeFrames = ref(null);
		const selectedItem = ref(0);

		onMounted(() => {
			timeFrames.value = [
				{ value: "daily", name: "Daily" },
				{ value: "weekly", name: "Weekly" },
				{ value: "monthly", name: "Monthly" }
			];
		});

		return { name, timeFrames, selectedItem };
	}
};
</script>

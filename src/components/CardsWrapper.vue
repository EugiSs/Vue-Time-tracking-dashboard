<template>
	<div class="app">
		<CardProfile @onChangeTimeFrame="changeTimeFrame"></CardProfile>
		<CardItem
			v-for="item of items"
			:key="item.type"
			:data="item"
			:timeFrame="timeFrame"
		></CardItem>
	</div>
</template>

<script>
import CardProfile from "@/components/CardProfile.vue";
import CardItem from "@/components/CardItem.vue";
import { GetItems } from "@/assets/items.js";
import { onMounted, ref } from "vue";

export default {
	components: { CardProfile, CardItem },
	props: {
		defaultTimeFrame: String
	},
	methods: {},
	setup(props) {
		const items = ref(null);
		const timeFrame = ref("");

		onMounted(() => {
			items.value = GetItems();
			timeFrame.value = props.defaultTimeFrame;
		});

		const changeTimeFrame = (value) => { //меняем отображаемые данные при смене времени
			timeFrame.value = value;
		};

		return { items, timeFrame, changeTimeFrame };
	}
};
</script>

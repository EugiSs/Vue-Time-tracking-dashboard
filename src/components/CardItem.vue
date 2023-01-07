<template>
	<section class="card" :class="data.type">
		<div class="card__topframe"></div>
		<div class="card__content">
			<div class="card__header">
				<p class="card__title">{{ data.title }}</p>
				<div class="card__img">
					<img src="@/img/icon-ellipsis.svg" alt="img" />
				</div>
			</div>
			<div class="card__hours">
				<div class="card__hours-current">
					{{ data.timeframes[timeFrame].current }}hrs
				</div>
				<div class="card__hours-last">
					{{ checkTimeFrame(timeFrame) }}
					{{ data.timeframes[timeFrame].previous }}hrs
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	props: {
		data: Object,
		timeFrame: String
	},
	setup() {
		const checkTimeFrame = (timeframe) => { //отображаем текст в зависимости от времени
			switch (timeframe) {
				case "daily":
					return "Last Day - ";
				case "weekly":
					return "Last Week - ";
				case "monthly":
					return "Last Month - ";
			}
		};
    return { checkTimeFrame };
	}
};
</script>

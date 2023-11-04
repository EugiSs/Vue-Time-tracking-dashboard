<template>
	<div class="wrapper">
		<main class="main">
			<CardsWrapper defaultTimeFrame="daily" />
		</main>
		<footer>
			<div class="attribution">
				Challenge by
				<a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
					>Frontend Mentor</a
				>. Coded by <a href="https://github.com/EugiSs">Eugi Ss</a>.
			</div>
		</footer>
	</div>
</template>

<script>
import CardsWrapper from "./components/CardsWrapper.vue";

export default {
	name: "App",
	components: {
		CardsWrapper
	}
};
</script>

<style></style>

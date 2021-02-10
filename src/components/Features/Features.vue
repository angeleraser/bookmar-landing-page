<template>
	<section class="features-wrapper">
		<header>
			<h1>Features</h1>
			<p>
				Lorem ipsum dolor sit, amet consectetur adipisicing elit. Obcaecati
				vero, eos harum minus earum repellendus qui aspernatur quos et!
				Recusandae, quidem expedita?
			</p>
		</header>
		<features-tab-panel v-on:getSelectedTabName="handleTabClick" />
		<features-tabs v-bind:selectedTab="selectedTab" />
	</section>
</template>

<script>
import FeaturesTabPanel from '../FeaturesTabPanel/FeaturesTabPanel.vue';
import FeaturesTabs from '../FeaturesTabs/FeaturesTabs.vue';
export default {
	components: { FeaturesTabPanel, FeaturesTabs },
	name: 'Features',
	data() {
		return {
			selectedTab: 'simple-bookmarking',
		};
	},
	methods: {
		handleTabClick(payload) {
			this.selectedTab = payload;
		},
	},
};
</script>

<style scoped>
.features-wrapper {
	font-family: var(--ff-rubik);
	width: 100%;
	padding-bottom: 160px;
}

.features-wrapper header {
	align-items: center;
	display: flex;
	flex-direction: column;
	margin-bottom: 44px;
	padding: 0 32px;
	text-align: center;
	width: 100%;
}

.features-wrapper header h1 {
	color: var(--very-dark-blue);
	font-size: 26px;
	font-weight: 500;
	margin-bottom: 12px;
	text-transform: capitalize;
}

.features-wrapper header p {
	color: var(--grayish-blue);
	line-height: 1.7;
	max-width: 528px;
}

@media screen and (min-width: 1024px) {
	.features-wrapper header h1 {
		font-size: 32px;
	}
}
</style>

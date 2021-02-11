<template>
	<section id="features" class="features-wrapper">
		<section-header
			:sectionTitle="'Features'"
			:description="
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia accusantium quisquam sit officiis velit accusamus?'
			"
		/>
		<features-tab-panel v-on:getSelectedTabName="handleTabClick" />
		<features-tabs v-bind:selectedTab="selectedTab" />
	</section>
</template>

<script>
import FeaturesTabPanel from '@/components/FeaturesTabPanel/FeaturesTabPanel.vue';
import FeaturesTabs from '@/components/FeaturesTabs/FeaturesTabs.vue';
import SectionHeader from '@/components/SectionHeader/SectionHeader.vue';
export default {
	components: { FeaturesTabPanel, FeaturesTabs, SectionHeader },
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
</style>

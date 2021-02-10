<template>
	<nav class="features-tab-panel">
		<ul>
			<li v-for="(tab, index) in tabNames" :key="index">
				<button
					:class="{ active: selectedTab === tab }"
					v-on:click="selectTab(tab)"
					class="tab-button"
				>
					{{ getTabName(tab) }}
				</button>
			</li>
		</ul>
	</nav>
</template>

<script>
export default {
	name: 'FeaturesTabPanel',
	data() {
		return {
			tabNames: ['simple-bookmarking', 'speedy-searching', 'easy-sharing'],
			selectedTab: 'simple-bookmarking',
		};
	},
	methods: {
		getTabName(name) {
			return name.split('-').join(' ');
		},
		selectTab(tab) {
			this.selectedTab = tab;
		},
	},
};
</script>

<style scoped>
.features-tab-panel {
	width: 100%;
	padding: 0 32px;
	margin-bottom: 72px;
}

.features-tab-panel ul {
	border-bottom: 1px solid var(--light-grayish-blue);
	border-top: 1px solid var(--light-grayish-blue);
	display: flex;
	flex-direction: column;
	width: 100%;
	max-width: 730px;
	margin: 0 auto;
}

.features-tab-panel ul li {
	align-items: center;
	display: inline-flex;
	justify-content: center;
	width: 100%;
}

.features-tab-panel ul li:not(:last-child) {
	border-bottom: 1px solid var(--light-grayish-blue);
}

.features-tab-panel li button {
	color: var(--grayish-blue);
	text-transform: capitalize;
	min-width: 162px;
	padding: 22px 0;
	position: relative;
}
.features-tab-panel li button::after {
	background-color: var(--soft-red);
	bottom: 0;
	content: '';
	display: inline-block;
	height: 4px;
	left: 0;
	position: absolute;
	width: 100%;
	transition: all 0.2s ease;
	transform: scale(0);
	transform-origin: center;
}

.features-tab-panel li button.active {
	color: var(--very-dark-blue);
}

.features-tab-panel li button.active::after {
	transform: scale(1);
}

@media screen and (min-width: 768px) {
	.features-tab-panel ul {
		flex-direction: row;
		border-top: none;
		padding: 0;
	}

	.features-tab-panel li button {
		min-width: 100%;
	}

	.features-tab-panel ul li {
		flex: 1 0;
	}

	.features-tab-panel ul li:not(:last-child) {
		border-bottom: none;
	}
}
</style>

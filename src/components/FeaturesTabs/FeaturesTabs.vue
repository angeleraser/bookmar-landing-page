<template>
	<div class="features-tabs">
		<div
			:key="'simple-bookmarking'"
			v-if="selectedTab === 'simple-bookmarking'"
			class="feature-item item-1"
		>
			<illustration class="feature-illustration" :position="'right'">
				<img
					src="@/assets/images/svg/illustration-features-tab-1.svg"
					alt="Illustration hero"
				/>
			</illustration>
			<div class="feature-info">
				<h2>Bookmark in one click</h2>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex cupiditate
					sequi excepturi quis similique, exercitationem veniam quia numquam ea
					fugiat atque consequuntur!
				</p>
				<button-base :color="'blue'">More Info</button-base>
			</div>
		</div>
		<div
			:key="'speedy-searching'"
			v-if="selectedTab === 'speedy-searching'"
			class="feature-item item-2"
		>
			<illustration class="feature-illustration" :position="'right'">
				<img
					src="@/assets/images/svg/illustration-features-tab-2.svg"
					alt="Illustration hero"
				/>
			</illustration>
			<div class="feature-info">
				<h2>Intelligent Search</h2>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex cupiditate
					sequi excepturi quis similique, exercitationem veniam quia numquam ea
					fugiat atque consequuntur!
				</p>
				<button-base :color="'blue'">More Info</button-base>
			</div>
		</div>
		<div
			:key="'easy-sharing'"
			v-if="selectedTab === 'easy-sharing'"
			class="feature-item item-3"
		>
			<illustration class="feature-illustration" :position="'right'">
				<img
					src="@/assets/images/svg/illustration-features-tab-3.svg"
					alt="Illustration hero"
				/>
			</illustration>
			<div class="feature-info">
				<h2>Share your bookmarks</h2>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex cupiditate
					sequi excepturi quis similique, exercitationem veniam quia numquam ea
					fugiat atque consequuntur!
				</p>
				<button-base :color="'blue'">More Info</button-base>
			</div>
		</div>
	</div>
</template>

<script>
import ButtonBase from '../Base/Button/ButtonBase.vue';
import Illustration from '../Illustration/Illustration.vue';
export default {
	components: { Illustration, ButtonBase },
	name: 'FeaturesTabs',
	props: {
		selectedTab: {
			type: String,
			required: true,
			default: 'simple-bookmarking',
		},
	},
};
</script>

<style scoped>
.features-tabs {
	width: 100%;
	overflow: hidden;
}

.feature-item {
	animation: slideInLeft 1s forwards ease;
}

@keyframes slideInLeft {
	from {
		transform: translateX(-100%);
	}
	to {
		transform: translateX(0);
	}
}

.features-tabs .feature-item,
.feature-item .feature-info {
	display: flex;
	flex-direction: column;
	align-items: center;
}

.feature-item .feature-info {
	margin-top: 80px;
	text-align: center;
	padding: 0 32px;
}

.features-tabs .feature-item h2 {
	color: var(--very-dark-blue);
	font-size: 26px;
	font-weight: 500;
	margin-bottom: 12px;
	text-transform: capitalize;
}

.features-tabs .feature-item p {
	color: var(--grayish-blue);
	line-height: 1.7;
	max-width: 528px;
}

.features-tabs .button-base {
	margin-top: 32px;
}

@media screen and (min-width: 1024px) {
	.features-tabs {
		min-height: 490px;
	}

	.features-tabs .feature-item {
		flex-direction: row;
		align-items: center;
	}

	.features-tabs .feature-info {
		text-align: left;
		align-items: flex-start;
		margin-left: 62px;
		padding: 0 32px 0 0;
		margin-top: 0;
	}
}

@media screen and (min-width: 1280px) {
	.features-tabs .feature-info {
		padding-right: 87px;
		margin-left: 0;
	}
}

@media screen and (min-width: 1440px) {
	.features-tabs .feature-info {
		padding-right: 174px;
	}
}
</style>

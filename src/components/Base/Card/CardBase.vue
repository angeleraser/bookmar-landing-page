<template>
	<article class="card-base">
		<div class="browser-details">
			<div class="icon">
				<slot />
			</div>
			<span class="name">{{ `Add to ${browser.name}` }}</span>
			<span class="version">{{ `Minimun version ${browser.version}` }}</span>
			<svg xmlns="http://www.w3.org/2000/svg" width="280" height="4">
				<path
					fill="#495DCF"
					fill-opacity=".2"
					fill-rule="evenodd"
					d="M0 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm280 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-17 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-18 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-17 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm122 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-70 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM88 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM70 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM53 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM35 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM18 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4z"
				/>
			</svg>
		</div>
		<div class="cta-button">
			<button-base :color="'blue'">Add & Install Extension</button-base>
		</div>
	</article>
</template>

<script>
import ButtonBase from '../Button/ButtonBase.vue';
export default {
	components: { ButtonBase },
	name: 'CardBase',
	props: {
		browser: {
			type: Object,
			required: true,
		},
	},
};
</script>

<style scoped>
.card-base,
.browser-details {
	display: flex;
	flex-direction: column;
	align-items: center;
}
.card-base {
	border-radius: 8px;
	box-shadow: 0 8px 12px rgba(0, 0, 0, 0.1);
	display: inline-block;
	width: 282px;
}

.card-base .browser-details {
	font-family: var(--ff-rubik);
	padding: 42px 0 0;
	width: 100%;
}

.card-base .browser-details .name {
	color: var(--very-dark-blue);
	font-size: 22px;
	font-weight: var(--fw-bold);
	margin-top: 38px;
}

.card-base .browser-details .version {
	color: var(--light-grayish-blue);
	margin: 14px 0 38px;
}

.card-base .cta-button {
	display: flex;
	justify-content: center;
	padding: 24px 0;
	width: 100%;
}
</style>

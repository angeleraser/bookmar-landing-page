<template>
	<button v-bind:class="buttonColor" class="button-base"><slot /></button>
</template>

<script>
export default {
	name: 'ButtonBase',
	data() {
		return {
			colorName: this.color,
		};
	},
	computed: {
		buttonColor() {
			return this.colorName;
		},
	},
	props: {
		color: {
			type: String,
			default: 'normal',
		},
	},
};
</script>

<style scoped>
.button-base {
	align-items: center;
	border-radius: 6px;
	border-style: solid;
	border-width: 2px;
	box-shadow: 0 4px 11px rgba(0, 0, 0, 0.1);
	display: inline-flex;
	font-family: 'Rubik', sans-serif;
	font-weight: var(--fw-bold);
	justify-content: center;
	letter-spacing: 2px;
	min-width: 112px;
	padding: 12px 24px;
	text-transform: uppercase;
	transition: all 0.1s linear;
}

.button-base:active {
	transform: scale(0.97);
}

.button-base.normal {
	background-color: transparent;
	border-color: var(--white);
	color: var(--white);
}

.button-base.red {
	background-color: var(--soft-red);
	border-color: var(--soft-red);
	color: var(--white);
}

.button-base.red:hover {
	background-color: var(--white);
	color: var(--soft-red);
}
</style>

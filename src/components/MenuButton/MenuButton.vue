<template>
	<button
		v-bind:class="classObject"
		v-on:click="toggleOpen"
		class="menu-button"
	>
		<span class="line"></span>
		<span class="line"></span>
		<span class="line"></span>
	</button>
</template>

<script>
export default {
	name: 'MenuButton',
	data() {
		return {
			isOpen: this.isActive,
		};
	},
	methods: {
		toggleOpen() {
			this.isOpen = !this.isOpen;
			this.$emit('getIsActive', this.isOpen);
		},
	},
	computed: {
		classObject() {
			return {
				active: this.isOpen,
			};
		},
	},
	props: {
		isActive: {
			type: Boolean,
			required: true,
			default: false,
		},
	},
};
</script>

<style>
.menu-button {
	align-items: center;
	display: flex;
	flex-direction: column;
	height: 16px;
	justify-content: space-between;
	position: relative;
	width: 20px;
	z-index: 10;
}

.menu-button .line {
	background-color: var(--very-dark-blue);
	height: 3px;
	width: 100%;
	transition: all 0.3s;
	position: absolute;
}

.menu-button.active .line {
	background-color: var(--white);
}

.menu-button .line:nth-child(2) {
	top: 50%;
	transform: translate(0, -50%);
}

.menu-button .line:nth-child(1) {
	top: 0;
}

.menu-button .line:nth-child(3) {
	bottom: 0;
}

.menu-button.active .line:nth-child(2) {
	opacity: 0;
}

.menu-button.active .line:nth-child(1) {
	top: 50%;
	transform: translate(0, -50%) rotate(45deg);
}

.menu-button.active .line:nth-child(3) {
	bottom: 50%;
	transform: translate(0, 50%) rotate(135deg);
}
</style>

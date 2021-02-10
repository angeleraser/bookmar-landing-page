<template>
	<div v-bind:class="classes" class="illustration-wrapper">
		<div class="img">
			<slot />
		</div>
	</div>
</template>

<script>
export default {
	name: 'Illustration',
	props: {
		position: {
			type: String,
			required: true,
			default: 'left',
		},
	},
	computed: {
		classes() {
			return [this.position];
		},
	},
};
</script>

<style>
.illustration-wrapper {
	display: flex;
	position: relative;
	height: 252px;
	width: 100%;
}

.illustration-wrapper .img {
	display: inline-block;
	z-index: 1;
	height: 100%;
}

.illustration-wrapper img {
	height: auto;
	object-fit: cover;
}

.illustration-wrapper::after {
	content: '';
	display: inline-block;
	width: calc(100% - 23.5%);
	height: 80.2%;
	background-color: var(--soft-blue);
	position: absolute;
	top: 100px;
}

.illustration-wrapper.left::after {
	right: 0;
	border-radius: 100px 0 0 100px;
}

.illustration-wrapper.right::after {
	left: 0;
	border-radius: 0 100px 100px 0;
}

.feature-item .feature-illustration.illustration-wrapper {
	padding-right: 32px;
}

.feature-item .img {
	padding-left: 32px;
}

.feature-item .illustration-wrapper img {
	object-fit: contain;
	height: 100%;
}

@media screen and (min-width: 480px) {
	.illustration-wrapper {
		height: 480px;
	}

	.illustration-wrapper.left::after {
		border-radius: 200px 0 0 200px;
	}

	.illustration-wrapper.right::after {
		border-radius: 0 200px 200px 0;
	}

	.feature-item .feature-illustration.illustration-wrapper {
		padding-right: 0;
	}

	.feature-item .img {
		padding-left: 32px;
		max-width: 90%;
	}

	.feature-item .illustration-wrapper img {
		object-fit: contain;
		max-height: 90%;
	}
}

@media screen and (min-width: 1024px) {
	.illustration-wrapper .img {
		position: absolute;
	}

	.illustration-wrapper.left .img {
		right: 80px;
	}

	.illustration-wrapper.right .img {
		left: 80px;
	}
}

@media screen and (min-width: 1280px) {
	.illustration-wrapper {
		min-width: 764px;
	}

	.feature-item .img {
		padding-left: 0;
	}

	.feature-item .illustration-wrapper img {
		height: 100%;
	}

	.feature-item.item-1 .illustration-wrapper .img {
		left: 140px;
	}

	.feature-item.item-2 .illustration-wrapper .img,
	.feature-item.item-3 .illustration-wrapper .img {
		left: 330px;
	}
}
</style>

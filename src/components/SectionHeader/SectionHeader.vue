<template>
	<header class="section-header">
		<h1>{{ sectionTitle }}</h1>
		<p>
			{{ description }}
		</p>
	</header>
</template>

<script>
export default {
	name: 'SectionHeader',
	props: {
		sectionTitle: {
			type: String,
			default: 'Lorem Ipsum',
			required: true,
		},
		description: {
			type: String,
			default:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis accusantium distinctio rem totam nam in aspernatur maxime voluptatem explicabo labore, at quaerat repudiandae odit! Veritatis quos quia quasi ab repellendus?',
			required: true,
		},
	},
};
</script>

<style>
.section-header {
	align-items: center;
	display: flex;
	flex-direction: column;
	margin-bottom: 44px;
	padding: 0 32px;
	text-align: center;
	width: 100%;
	font-family: var(--ff-rubik);
}

.section-header h1 {
	color: var(--very-dark-blue);
	font-size: 26px;
	font-weight: 500;
	margin-bottom: 12px;
	text-transform: capitalize;
}

.section-header p {
	color: var(--grayish-blue);
	line-height: 1.7;
	max-width: 528px;
}

@media screen and (min-width: 1024px) {
	.section-header h1 {
		font-size: 32px;
	}

	.download-extension .section-header {
		margin-bottom: 0;
	}
}
</style>

<template>
	<main class="main">
		<features />
	</main>
</template>

<script>
import Features from '../Features/Features.vue';
export default {
	components: { Features },
	name: 'AppMain',
};
</script>

<style scoped>
.main {
	align-items: flex-start;
	display: flex;
	flex-direction: column;
	padding: 156px 0 0;
	width: 100%;
}

@media screen and (min-width: 768px) {
	.main {
		padding: 100px 0 0;
	}
}
</style>

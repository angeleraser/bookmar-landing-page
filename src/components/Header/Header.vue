<template>
	<header>
		<header-nav />
		<header-section />
	</header>
</template>

<script>
import HeaderNav from '@/components/HeaderNav/HeaderNav.vue';
import HeaderSection from '@/components/HeaderSection/HeaderSection.vue';
export default {
	components: { HeaderNav, HeaderSection },
	name: 'AppHeader',
};
</script>

<style scoped>
header {
	align-items: center;
	display: flex;
	flex-direction: column;
	width: 100%;
}
</style>

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
	position: relative;
}
</style>

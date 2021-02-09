<template>
	<header>
		<header-nav />
	</header>
</template>

<script>
import HeaderNav from '../HeaderNav/HeaderNav.vue';
export default {
	components: { HeaderNav },
	name: 'AppHeader',
};
</script>

<style scoped>
header {
	position: relative;
}
</style>

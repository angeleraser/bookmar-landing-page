<template>
	<div id="app">
		<app-header />
		<app-main />
		<app-footer />
	</div>
</template>

<script>
import '@/assets/styles/App.css';
import AppHeader from '@/components/Header/Header.vue';
import AppMain from '@/components/Main/Main.vue';
import AppFooter from '@/components/Footer/Footer.vue';

export default {
	components: { AppHeader, AppMain, AppFooter },
	name: 'App',
};
</script>

<style></style>

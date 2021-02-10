<template>
	<div id="app">
		<app-header />
		<app-main />
	</div>
</template>

<script>
import '@/assets/styles/App.css';
import AppHeader from '@/components/Header/Header.vue';
import AppMain from '@/components/Main/Main.vue';

export default {
	components: { AppHeader, AppMain },
	name: 'App',
};
</script>

<style></style>

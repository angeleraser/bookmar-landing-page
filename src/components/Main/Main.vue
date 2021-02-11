<template>
	<main class="main">
		<features />
		<download-extension />
		<faq-section />
		<contact-us />
	</main>
</template>

<script>
import DownloadExtension from '@/components/DownloadExtension/DownloadExtension.vue';
import FaqSection from '@/components/FAQ/FaqSection.vue';
import Features from '@/components/Features/Features.vue';
import ContactUs from '@/components/ContactUs/ContactUs.vue';
export default {
	components: { Features, DownloadExtension, FaqSection, ContactUs },
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

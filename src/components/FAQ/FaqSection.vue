<template>
	<section class="faq-section">
		<section-header
			:sectionTitle="'Frequently Asked Questions'"
			:description="
				'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Possimus rerum dignissimos eos error dolores!'
			"
		/>
		<questions-list />
	</section>
</template>

<script>
import QuestionsList from '@/components/QuestionsList/QuestionsList.vue';
import SectionHeader from '@/components/SectionHeader/SectionHeader.vue';
export default {
	components: { SectionHeader, QuestionsList },
};
</script>

<style>
.faq-section {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 100%;
	padding-bottom: 118px;
}

.faq-section .section-header p {
	max-width: 480px;
}

@media screen and (min-width: 1024px) {
	.faq-section {
		padding-bottom: 142px;
	}
}
</style>

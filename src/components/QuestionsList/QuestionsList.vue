<template>
	<div class="questions-list">
		<question-item
			v-for="({ quest, answer }, index) in questions"
			:key="index"
			:quest="quest"
			:answer="answer"
		/>
		<button-base :color="'blue'">More Info</button-base>
	</div>
</template>

<script>
import ButtonBase from '@/components/Base/Button/ButtonBase.vue';
import QuestionItem from '@/components/QuestionItem/QuestionItem.vue';
import { questions } from '@/fixtures/faq-quests.js';
export default {
	components: { QuestionItem, ButtonBase },
	name: 'QuestionsList',
	data() {
		return {
			questions,
		};
	},
};
</script>

<style scoped>
.questions-list {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 0 32px;
	max-width: 544px;
}

.questions-list .button-base {
	margin-top: 48px;
}
</style>

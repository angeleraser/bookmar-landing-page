<template>
	<article :style="questionStyle" class="question-item">
		<header>
			<button
				v-on:click="openQuestion"
				:class="classObject"
				class="quest-button"
			>
				<span>{{ quest }}</span>
				<svg xmlns="http://www.w3.org/2000/svg" width="18" height="12">
					<path
						fill="none"
						stroke="currentColor"
						stroke-width="3"
						d="M1 1l8 8 8-8"
					/>
				</svg>
			</button>
		</header>
		<p ref="answer" class="answer">
			{{ answer }}
		</p>
	</article>
</template>

<script>
export default {
	name: 'QuestionItem',
	data() {
		return {
			isOpen: true,
			styleObject: {
				height: 72,
			},
		};
	},
	computed: {
		classObject() {
			return {
				[`is-open`]: this.isOpen,
			};
		},
		questionStyle() {
			return {
				...this.styleObject,
				height: `${this.styleObject.height}px`,
			};
		},
	},
	methods: {
		openQuestion() {
			this.isOpen = !this.isOpen;

			const answerContainerHeight = this.$refs.answer.getBoundingClientRect()
				.height;

			const headerHeight = 72;

			const paddingBottom = 34;

			if (!this.isOpen) {
				this.styleObject.height =
					headerHeight + answerContainerHeight + paddingBottom;
			} else {
				this.styleObject.height = headerHeight;
			}
		},
	},
	props: {
		quest: {
			type: String,
			required: true,
		},
		answer: {
			type: String,
			required: true,
		},
	},
};
</script>

<style scoped>
.question-item {
	align-items: flex-start;
	border-top: 1px solid var(--light-grayish-blue);
	display: flex;
	flex-direction: column;
	font-family: var(--ff-rubik);
	width: 100%;
	height: 72px;
	overflow: hidden;
	transition: height 0.4s ease;
}

.question-item:first-child {
	border-bottom: none;
}

.question-item:last-of-type {
	border-bottom: 1px solid var(--light-grayish-blue);
}

.question-item header {
	width: 100%;
}

.question-item header button {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 26px 0;
	width: 100%;
}

.question-item header button:hover span {
	color: var(--soft-red);
}

.question-item header button span {
	color: var(--very-dark-blue);
	font-size: 18px;
	transition: all 0.4s ease;
}

.question-item .answer {
	color: var(--grayish-blue);
	line-height: 1.7;
}

.question-item .quest-button svg {
	color: var(--soft-blue);
	transition: all 0.6s ease;
}

.question-item .quest-button.is-open svg {
	transform: rotateX(180deg);
	color: var(--soft-red);
}
</style>

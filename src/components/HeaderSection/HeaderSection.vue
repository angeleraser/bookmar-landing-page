<template>
	<section class="header-section">
		<illustration :position="illustrationPosition">
			<img
				src="@/assets/images/svg/illustration-hero.svg"
				alt="Illustration hero"
			/>
		</illustration>

		<div class="section-info">
			<h1>A simple bookmark manager</h1>
			<p>
				A clean simple interface to organize your favorites websites. Open a new
				browser tab and see your sites load instantly. Try it for free
			</p>
		</div>
	</section>
</template>

<script>
import ButtonBase from '../Base/Button/ButtonBase.vue';
import Illustration from '../Illustration/Illustration.vue';
export default {
	name: 'HeaderSection',
	components: { Illustration, ButtonBase },
	data() {
		return {
			illustrationPosition: 'left',
		};
	},
};
</script>

<style>
.section-info,
.header-section {
	align-items: flex-start;
	display: flex;
	flex-direction: column;
	width: 100%;
}

.section-info {
	font-family: var(--ff-rubik);
	margin: 100px 0 0;
	padding: 0 32px;
	text-align: center;
}

.section-info h1 {
	color: var(--very-dark-blue);
	font-size: 32px;
	font-weight: var(--fw-bold);
	text-transform: capitalize;
	width: 100%;
	margin-bottom: 12px;
}

.section-info p {
	color: var(--grayish-blue);
	line-height: 1.7;
	max-width: 480px;
}

@media screen and (min-width: 768px) {
	.section-info {
		margin: 50px 0 0;
	}

	.section-info h1 {
		font-size: 36px;
	}

	.section-info p {
		font-size: 18px;
	}
}

@media screen and (min-width: 768px) {
	.section-info {
		text-align: left;
	}
}
</style>

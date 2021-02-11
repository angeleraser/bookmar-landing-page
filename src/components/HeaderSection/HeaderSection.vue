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

			<div class="cta-buttons">
				<button-base :color="'blue'">Get it on Chrome</button-base>
				<button-base :color="'white'">Get it on Firefox</button-base>
			</div>
		</div>
	</section>
</template>

<script>
import ButtonBase from '@/components/Base/Button/ButtonBase.vue';
import Illustration from '@/components/Illustration/Illustration.vue';
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
.header-section {
	margin-top: 38px;
}

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
	align-items: center;
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

.cta-buttons {
	align-items: center;
	display: flex;
	justify-content: center;
	margin-top: 36px;
	width: 100%;
}

.cta-buttons .button-base {
	font-size: 14px;
	padding: 12px 14px;
}

.cta-buttons .button-base:first-child {
	margin-right: 16px;
}

@media screen and (min-width: 768px) {
	.section-info {
		margin: 50px 0 0;
		align-items: flex-start;
	}

	.section-info h1 {
		font-size: 36px;
	}

	.section-info p {
		font-size: 18px;
	}

	.cta-buttons {
		justify-content: flex-start;
	}

	.cta-buttons .button-base {
		font-size: 16px;
		padding: 12px 24px;
	}
}

@media screen and (min-width: 768px) {
	.section-info {
		text-align: left;
	}
}

@media screen and (min-width: 1280px) {
	.header-section {
		flex-direction: row-reverse;
		align-items: center;
		margin-top: 68px;
	}

	.section-info {
		padding: 0 0 0 87px;
		margin: 0;
	}

	.section-info h1 {
		font-size: 48px;
	}
}

@media screen and (min-width: 1440px) {
	.section-info {
		padding: 0 0 0 174px;
		margin: 0;
	}

	.section-info h1 {
		font-size: 58px;
	}
}
</style>

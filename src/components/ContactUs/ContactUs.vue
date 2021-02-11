<template>
	<section id="contact-us" class="contact-us">
		<h1>
			<span>35,000 + already joined</span> Stay up-to-date with what we're doing
		</h1>
		<form v-on:submit.prevent="onFormSubmit">
			<label :class="labelClassObject" for="email">
				<input
					placeholder="Enter your email address"
					type="text"
					name="email"
					v-model.trim="inputValue"
					v-on:keydown="removeInvalidStyles"
				/>
				<span v-if="isInvalid" class="error-message"
					>Whoops, make sure it's an email</span
				>
				<svg
					class="icon-error"
					xmlns="http://www.w3.org/2000/svg"
					width="20"
					height="20"
				>
					<g fill="none" fill-rule="evenodd">
						<circle cx="10" cy="10" r="10" fill="#FA5959" />
						<g fill="#FFF" transform="translate(9 5)">
							<rect width="2" height="7" rx="1" />
							<rect width="2" height="2" y="8" rx="1" />
						</g>
					</g>
				</svg>
			</label>
			<button-base :color="'red'">Contact Us</button-base>
		</form>
	</section>
</template>

<script>
import ButtonBase from '../Base/Button/ButtonBase.vue';
export default {
	components: { ButtonBase },
	data() {
		return {
			isInvalid: false,
			inputValue: '',
		};
	},
	methods: {
		onFormSubmit() {
			if (!/[@.]/.test(this.inputValue)) {
				this.isInvalid = true;
			}
		},
		removeInvalidStyles() {
			if (this.isInvalid) {
				this.isInvalid = false;
			}
		},
	},
	computed: {
		labelClassObject() {
			return [{ invalid: this.isInvalid }, 'input-label'];
		},
	},
};
</script>

<style scoped>
.contact-us h1,
.contact-us,
.contact-us form,
.contact-us form label {
	display: flex;
	align-items: center;
	flex-direction: column;
	width: 100%;
	max-width: 405px;
}

.contact-us {
	background-color: var(--soft-blue);
	padding: 70px 32px 36px;
	font-family: var(--ff-rubik);
	width: 100%;
	max-width: 100%;
}

.contact-us h1 {
	color: var(--white);
	font-size: 26px;
	margin: 0 0 30px;
	font-weight: var(--fw-bold);
	text-align: center;
}

.contact-us h1 span {
	font-size: 12px;
	letter-spacing: 4px;
	margin-bottom: 18px;
	text-transform: uppercase;
}

.contact-us form label {
	background-color: transparent;
	border-radius: 6px;
	border-bottom-left-radius: 0;
	border-bottom-right-radius: 0;
	padding: 2px 2px;
	position: relative;
}

.contact-us form label.invalid {
	background-color: var(--soft-red);
	margin-bottom: 18px;
}

.contact-us form .error-message {
	background-color: var(--soft-red);
	border-bottom-left-radius: 6px;
	border-bottom-right-radius: 6px;
	bottom: 0;
	color: var(--white);
	font-size: 10px;
	font-style: italic;
	font-weight: var(--fw-bold);
	padding: 4px;
	position: absolute;
	transform: translateY(100%);
	width: 100%;
}

.contact-us form label input {
	border-radius: 4px;
	border: none;
	color: var(--very-dark-blue);
	height: 48px;
	outline: none;
	padding: 0 35px 0 20px;
	width: 100%;
}

.contact-us form label input::placeholder {
	color: var(--grayish-blue);
	font-family: var(--ff-rubik);
}

.contact-us label .icon-error {
	position: absolute;
	right: 14px;
	top: 50%;
	transform: translateY(-50%) scale(0);
	transition: 0.2s ease all;
	transform-origin: 50% 20px;
}

.contact-us label.invalid .icon-error {
	transform: translateY(-50%) scale(1);
}

.contact-us form label input:focus {
	outline: none;
}

.contact-us form .button-base {
	width: 100%;
	margin-top: 16px;
}

@media screen and (min-width: 768px) {
	.contact-us {
		padding: 72px 0;
	}

	.contact-us form {
		flex-direction: row;
		align-items: stretch;
	}

	.contact-us form .button-base {
		margin-top: 0;
		margin-left: 14px;
		width: auto;
		flex-shrink: 0;
	}

	.contact-us h1 span {
		margin-bottom: 34px;
	}

	.contact-us h1 {
		margin: 0 0 36px;
		font-size: 30px;
	}

	.contact-us form label.invalid {
		margin-bottom: 0;
	}
}
</style>

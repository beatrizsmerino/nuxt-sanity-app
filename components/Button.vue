<template>
	<component
		:is="checkTag"
		:href="href"
		:to="to"
		:value="value"
		class="button"
		@click="eventClick"
	>
		<slot />
	</component>
</template>

<script>
	export default {
		name: 'Button',
		props: {
			href: {
				type: String,
				default: null
			},
			to: {
				type: String,
				default: null
			},
			value: {
				type: String,
				default: null
			}
		},
		computed: {
			checkTag() {
				if (this.href) {
					return 'a';
				} else if (this.to) {
					return 'nuxt-link';
				} else if (this.value) {
					return 'input';
				}

				return 'button';
			}
		},
		methods: {
			eventClick() {
				this.$emit('event-click');
			}
		}
	};
</script>

<style lang="scss" scoped>
	.button {
		padding: 1.2rem 2rem;
		display: flex;
		align-items: center;
		justify-content: center;
		text-decoration: none;
		text-transform: capitalize;
		text-align: center;
		font-size: 1.6rem;
		font-weight: 900;
		line-height: 110%;
		color: $color-black;
		border: 0.2rem solid transparent;
		border-radius: 0.5rem;
		outline: none;
		background-color: transparent;
		box-shadow: 0.5rem 0.5rem 1rem rgba($color-black, 0.2);
		user-select: none;
		cursor: pointer;
		appearance: none;

		> * {
			pointer-events: none;
		}

		&--icon {
			padding: 0;
			border: none;
			box-shadow: none;

			&:hover {
				color: $color-black;
				background-color: transparent;
			}
		}

		&--dark {
			border-color: $color-brand-3;
			color: $color-brand-3;

			&.nuxt-link-active,
			&:hover {
				color: $color-white;
				background-color: $color-brand-3;
			}
		}

		&--black {
			color: $color-black;
			border-color: $color-black;

			&.nuxt-link-active,
			&:hover {
				color: $color-white;
				border-color: $color-black;
				background-color: $color-black;
			}
		}

		&--success {
			color: $color-white;
			border-color: $color-success;
			background-color: $color-success;
		}

		&--error {
			color: $color-white;
			border-color: $color-error;
			background-color: $color-error;
		}
	}
</style>

<template>
	<header class="header page__inner">
		<div class="header__inner page__container">
			<nav
				class="header-nav"
				:class="{ 'is-open': isOpen }"
			>
				<ul class="header-nav__list">
					<li class="header-nav__item">
						<nuxt-link
							to="/"
							class="header-nav__link"
							exact
						>
							Home
						</nuxt-link>
					</li>
					<li class="header-nav__item">
						<nuxt-link
							to="/about"
							class="header-nav__link"
						>
							About
						</nuxt-link>
					</li>
				</ul>

				<Button
					class="header-nav__button button--icon"
					@event-click="openCloseNav"
				>
					<Icon
						v-if="!isOpen"
						icon-id="icon-menu"
						icon-aria-label="Open menu"
					/>
					<Icon
						v-else
						icon-id="icon-close"
						icon-aria-label="Close menu"
					/>
				</Button>
			</nav>
		</div>
	</header>
</template>

<script>
	import Button from '@/components/Button';
	import Icon from '@/components/Icon';

	export default {
		name: 'Header',
		components: {
			Button,
			Icon
		},
		data() {
			return {
				isOpen: false
			};
		},
		watch: {
			$route(to, from) {
				if (to != from) {
					this.closeNav();
				}
			}
		},
		methods: {
			openCloseNav() {
				this.isOpen = !this.isOpen;
			},
			closeNav() {
				this.isOpen = false;
			}
		}
	};
</script>

<style lang="scss" scoped>
	.header {
		height: 6rem;
		display: flex;
		align-items: center;

		&__inner {
			display: flex;
			justify-content: flex-end;
		}
	}

	.header-nav {
		display: flex;
		font-size: 2rem;

		@include media('md') {
			font-size: 4rem;
		}

		&__list {
			display: flex;
			align-items: center;
			list-style: none;
			transition: transform 0.5s ease-in-out 0s;

			@include media('md') {
				width: 100%;
				height: 100%;
				padding: 8rem 5% 3rem;
				flex-direction: column;
				position: fixed;
				top: 0;
				left: 0;
				z-index: 999999;
				transform: translate3d(100%, 0, 0);
				background: linear-gradient(
					-45deg,
					$color-brand-2 0%,
					$color-brand-1 90%
				);
			}

			@include media('md') {
				flex-direction: column;
			}
		}

		&__item {
			position: relative;

			&:not(:last-child) {
				margin-right: 2rem;

				@include media('md') {
					margin-right: 0;
					margin-bottom: 3rem;
				}
			}
		}

		&__link {
			padding: 0.5rem;
			color: rgba($color-white, 0.7);

			&:after {
				content: '';
				display: inline-block;
				width: 100%;
				height: 0.2rem;
				position: absolute;
				bottom: 0;
				left: 0;
				background-color: transparent;

				@include media('md') {
					height: 0.3rem;
				}
			}

			&:hover {
				color: $color-white;
			}

			&.nuxt-link-exact-active,
			&.nuxt-link-active {
				color: $color-white;

				&:after {
					background-color: $color-white;
				}
			}
		}

		/deep/ {
			.header-nav {
				&__button {
					display: none;
					margin-left: 4rem;
					position: relative;
					z-index: 999999;

					@include media('md') {
						display: inline-block;
					}

					.icon {
						&__use {
							fill: $color-white;
						}
					}

					.icon-menu {
						width: 3rem;
						height: 3rem;
					}

					.icon-close {
						width: 2.5rem;
						height: 2.5rem;
					}
				}
			}
		}

		&.is-open {
			.header-nav {
				&__list {
					transform: translate3d(0, 0, 0);
				}
			}
		}
	}
</style>

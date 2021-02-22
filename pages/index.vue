<template>
	<section class="page-section page__inner">
		<div class="page-section__content page__container">
			<Logo class="logo" />
			<h1 class="title">
				nuxt-sanity-app
			</h1>
			<div class="subtitle">
				<p>
					App development with nuxt.js and sanitity.io
				</p>
			</div>
			<div class="list">
				<Button
					href="https://www.sanity.io/"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--dark"
				>
					Documentation<br>
					SANITY.IO
				</Button>
				<Button
					href="https://nuxtjs.org/"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--dark"
				>
					Documentation<br>
					NUXT.JS
				</Button>
				<Button
					href="https://github.com/nuxt/nuxt.js"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--black"
				>
					GitHub<br>
					NUXT.JS
				</Button>
			</div>
		</div>
	</section>
</template>

<script>
	import Button from '@/components/Button';

	export default {
		components: {
			Button
		}
	};
</script>

<style lang="scss">
	.page-index {
		.page-main {
			display: flex;
			justify-content: center;
			align-items: center;
		}

		.page-section {
			height: 100%;
			display: flex;
			justify-content: center;
			align-items: center;

			&__content {
				height: 100%;
				display: flex;
				justify-content: center;
				align-items: center;
				flex-direction: column;
				text-align: center;
			}
		}

		.logo {
			width: 24.5rem;
			height: 18rem;
			margin: 0 auto 4rem;
		}

		.title {
			margin-bottom: 2rem;
			font-family: $font-brand-1;
			font-weight: 400;
			line-height: 100%;
			font-size: 7rem;
			color: $color-brand-4;

			@include media('md') {
				font-size: 5rem;
			}
		}

		.subtitle {
			font-family: $font-brand-2;
			font-weight: 300;
			line-height: 100%;
			font-size: 3rem;
			color: $color-light;
		}

		.list {
			width: 100%;
			margin-top: 4rem;
			display: flex;
			flex-wrap: wrap;
			align-items: center;
			justify-content: center;

			@include media('md') {
				flex-direction: column;
			}

			/deep/ {
				.button {
					@include media('md') {
						width: 40rem;
					}

					@include media('sm') {
						width: 90%;
					}

					&:not(:last-child) {
						margin-right: 2rem;

						@include media('md') {
							margin-right: 0;
							margin-bottom: 2rem;
						}
					}
				}
			}
		}
	}
</style>

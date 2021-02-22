<template>
	<div class="container">
		<div>
			<Logo />
			<h1 class="title">
				nuxt-sanity-app
			</h1>
			<div class="subtitle">
				<p>
					App development with nuxt.js and sanitity.io
				</p>
			</div>
			<div class="button__list">
				<a
					href="https://www.sanity.io/"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--dark"
				>
					Documentation<br>
					SANITY.IO
				</a>
				<a
					href="https://nuxtjs.org/"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--dark"
				>
					Documentation<br>
					NUXT.JS
				</a>
				<a
					href="https://github.com/nuxt/nuxt.js"
					target="_blank"
					rel="noopener noreferrer"
					class="button button--black"
				>
					GitHub<br>
					NUXT.JS
				</a>
			</div>
		</div>
	</div>
</template>

<script>
	export default {};
</script>

<style lang="scss">
	.container {
		margin: 0 auto;
		padding: 1rem 5%;
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
	}

	.title {
		margin-bottom: 2rem;
		font-family: $font-brand-1;
		font-weight: 400;
		font-size: 7rem;
		color: $color-brand-4;

		@include media('md') {
			font-size: 5rem;
		}
	}

	.subtitle {
		font-family: $font-brand-2;
		font-weight: 300;
		font-size: 3rem;
		color: $color-light;
	}
</style>

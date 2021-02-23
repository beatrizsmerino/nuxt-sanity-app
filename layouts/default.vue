<template>
	<div class="sticky__layout">
		<Header class="sticky__header" />
		<main class="page-main sticky__main">
			<Nuxt />
		</main>
		<Footer />
	</div>
</template>

<script>
	export default {
		head() {
			return {
				htmlAttrs: {
					class: `page-${this.$route.name}`
				}
			};
		}
	};
</script>

<style lang="scss">
	// PARTIALS SASS
	// =================================================
	@import '~/assets/scss/base/base-reset';
	@import '~/assets/scss/base/base-global';
	// =================================================
	@import '~/assets/scss/components/components-page';
	@import '~/assets/scss/components/components-sticky';
	// ------------------
	@import '~/assets/scss/components/components-nuxt-error';
</style>

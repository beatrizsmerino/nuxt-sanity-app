<template>
	<footer class="footer page__inner">
		<div class="footer__inner page__container">
			<p class="footer__copyright">
				@Copyright {{ getCurrentYear }}
			</p>
		</div>
	</footer>
</template>

<script>
	export default {
		name: 'Footer',
		computed: {
			getCurrentYear() {
				return new Date().getFullYear();
			}
		}
	};
</script>

<style lang="scss" scoped>
	.footer {
		font-size: 1.4rem;
		display: flex;
		justify-content: center;
		align-items: center;

		&__inner {
			padding: 2rem 0;
		}

		&__copyright {
			text-align: center;
		}
	}
</style>

<template>
	<i
		:class="`${iconId} icon`"
		:aria-label="iconAriaLabel"
	>
		<svg class="icon__svg">
			<use
				class="icon__use"
				:xlink:href="`#${iconId}`"
			/>
		</svg>
	</i>
</template>

<script>
	export default {
		name: 'Icon',
		props: {
			iconId: {
				type: String,
				required: true
			},
			iconAriaLabel: {
				type: String,
				required: true
			}
		},
		data() {
			return {};
		}
	};
</script>

<style lang="scss" scoped>
	.icon {
		width: 1.6rem;
		height: 1.6rem;
		display: flex;
		align-items: center;
		justify-content: center;

		&__svg {
			width: 100%;
			height: 100%;
			display: inline-block;
		}

		&__use {
		}
	}
</style>

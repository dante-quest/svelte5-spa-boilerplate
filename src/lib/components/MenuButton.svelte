<script lang="ts">
	import { goto } from "$app/navigation";

	let {
		title = "Title",
		navigateTo = undefined,
		divider = true,
		dividerColor = "var(--pico-primary)",
		dividerPadding = undefined,
		stylingReset = false,
		btnColor = undefined,
		btnColorCls = "primary",
		textColor = undefined,
		outline = false,
		children = undefined,
	} = $props();

	// Sets default divider padding or uses the user-set value
	dividerPadding = !divider
		? (!dividerPadding ? "5px" : dividerPadding)
		: (!dividerPadding ? "10px" : dividerPadding)
	;

	// Helper to style the button based on user-defined props values
	const useCustomBtnColor = btnColor ? true : false;
	const textColorStyle = textColor ? `color: ${textColor};` : "";

	/**
	 * Moves to target page programmatically if navigateTo has been set
	 */
	const performNavigation = () => {
		if(!navigateTo) return;
		goto(navigateTo);
	};
</script>

<button
	class:stylingReset={stylingReset}
	class={btnColorCls}
	class:btnCustomColors={useCustomBtnColor}
	class:outline={outline}
	style="{textColorStyle} --MenuButton-divider-color: {dividerColor}; --dividerPadding: {dividerPadding}; --pico-custom-color: {btnColor};"
	onclick={performNavigation}
>
	{#if children}
		<div
			class:iconDivider={divider}
		>
			{@render children()}
		</div>
	{/if}
	<div>
		{title}
	</div>
</button>

<style>
	button {
		display: flex;
		padding: 0px;

		div {
			padding: calc(var(--pico-nav-link-spacing-vertical) - var(--pico-border-width) * 2) var(--pico-nav-link-spacing-horizontal);
		}
		div:first-child {
			padding-right: var(--dividerPadding);
		}
		div:last-child {
			padding-left: var(--dividerPadding);
		}
	}

	.iconDivider {
		border-right: 1px solid var(--MenuButton-divider-color);
	}
	.stylingReset {
		border: none;
		background-color: initial;
		box-shadow: none;		
	}
	.btnCustomColors {
		background-color: var(--pico-custom-color);
		border-color: var(--pico-custom-color);
	}
</style>
<script lang="ts">
	import favicon from "$lib/assets/favicon.svg";
	import "@yohns/picocss/css/pico.violet.min.css";
	import "@yohns/picocss/css/pico.colors.min.css";
	import MenuButton from "$lib/components/MenuButton.svelte";
	import { House, TestTubeDiagonal  } from "@lucide/svelte";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<header>
	<nav>
		<ul>
			<li>
				<MenuButton
					title="Svelte 5 Kit Boilerplate"
					navigateTo="/"
				>
					<House />
				</MenuButton>
			</li>
		</ul>

		<ul>
			<li>
				<MenuButton
					title="Test Page"
					navigateTo="/test"
				>
				</MenuButton>
			</li>
			<li>
				<MenuButton
					title="Test Page"
					navigateTo="/test"
					divider={false}
					stylingReset={true}
				>
					<TestTubeDiagonal />
				</MenuButton>
			</li>
			<li>
				<MenuButton
					title="Test Page"
					navigateTo="/test"
					btnColorCls="secondary"
					outline={true}
					divider={false}
				>
					<House />
				</MenuButton>
			</li>
			<li>
				<MenuButton
					title="Test Page"
					navigateTo="/test"
					btnColor="#A000A0"
					textColor="#F2DF0D"
					divider={false}
				>
					<House />
				</MenuButton>
			</li>
		</ul>
	</nav>
</header>

<main>
	{@render children?.()}
</main>

<style>
nav {
	background-color: var(--pico-color-violet-850);
	margin-bottom: 15px;
	padding-left: 15px;
	padding-right: 15px;
}
main {
	padding-left: 15px;
	padding-right: 15px;
}
</style>
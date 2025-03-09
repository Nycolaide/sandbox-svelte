<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';

	import '@fontsource/geist-sans/100.css';
	import '@fontsource/geist-sans/200.css';
	import '@fontsource/geist-sans/300.css';
	import '@fontsource/geist-sans/400.css';
	import '@fontsource/geist-sans/500.css';
	import '@fontsource/geist-sans/600.css';
	import '@fontsource/geist-sans/700.css';
	import '@fontsource/geist-sans/800.css';
	import '@fontsource/geist-sans/900.css';

	// icons
	import 'mingcute_icon/font/Mingcute.css';

	import { App } from 'mytril/components';
	import Rgpd from '$lib/components/rgpd.svelte';

	let { children } = $props();
</script>

<App>
	<div class="app">
		<Header />

		learn-optimisation

		<main>
			{@render children()}
		</main>

		<footer>
			<p>
				visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to learn about SvelteKit
			</p>
		</footer>
	</div>

	<Rgpd />
</App>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>

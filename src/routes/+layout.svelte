<script lang="ts">
	import '../app.postcss';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { AppShell, LightSwitch, storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<AppShell>
	<svelte:fragment slot="header">
		<nav class="flex justify-between p-4">
			<a href="/" class="btn h1 font-bold italic">logo</a>
			<div class="flex gap-8 font-semibold my-auto">
				<a class="btn h5" href="/pricing">Pricing</a>
				<a class="btn h5" href="/pricing">Features</a>
			</div>
			<a href="https://app.taskforge.com" class="btn variant-ghost-primary font-bold my-auto"
				>Dashboard</a
			>
		</nav>
	</svelte:fragment>
	<slot />
</AppShell>

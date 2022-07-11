<script lang="ts">
	import { onMount } from 'svelte';

	let show = false;
	onMount(() => (show = true));
	export let delay = 0;
	export let text: string = '';

	function typewriter(node, { speed = 5 }) {
		const valid = node.childNodes.length === 1 && node.childNodes[0].nodeType === Node.TEXT_NODE;

		if (!valid) {
			throw new Error(`This transition only works on elements with a single text node child`);
		}

		const text = node.textContent;
		const duration = text.length / (speed * 0.01);

		return {
			duration,
			delay,
			tick: (t) => {
				const i = Math.trunc(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
	}
</script>

{#if show}
	<p transition:typewriter>{@html text}</p>
{/if}

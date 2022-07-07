<script lang="ts">
	import { onMount } from 'svelte';

	export let speed = 100;
	export let delay = 0;
	export let text: string = '';
	export let loop = false;

	let p = 0;
	$: shownText = text.slice(0, p);
	let interval;

	onMount(() => {
		setTimeout(() => {
			interval = setInterval(() => {
				p++;
			}, speed);
		}, delay);

		if (loop) {
			setTimeout(() => {
				clearInterval(interval);
				p = 0;

				setTimeout(() => {
					interval = setInterval(() => {
						p++;
					}, speed);
				}, delay);
			}, 30000);
		}
	});
</script>

{@html shownText}

<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<button>
	{@render children()}
</button>

<style>
	button {
		width: 200px;
		height: 40px;

		background-color: aquamarine;
	}
</style>

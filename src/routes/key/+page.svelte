<script lang="ts">
	import { fade } from 'svelte/transition';

	let count = $state(0);
</script>

<h1>key</h1>

<input type="number" value={count} onchange={(e) => (count = Number(e.currentTarget.value))} />

{#key count}
	<div class="h-8 w-8 bg-fuchsia-100" transition:fade>{count}</div>
{/key}

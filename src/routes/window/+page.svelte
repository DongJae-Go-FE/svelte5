<script lang="ts">
	function handleKeydown(event: KeyboardEvent) {
		alert(`pressed the ${event.key} key`);
	}

	let y = $state(0);

	$effect(() => {
		console.log(y, '테스트');
	});
</script>

<h1>window</h1>
window.addEventListener
<div></div>
<svelte:window onkeydown={handleKeydown} bind:scrollY={y} />

<style>
	div {
		height: 200dvh;
	}
</style>

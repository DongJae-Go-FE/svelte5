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

문서
<!-- <svelte:document onvisibilitychange={handleVisibilityChange} use:someAction /> -->
바디
<!-- <svelte:body onmouseenter={handleMouseenter} onmouseleave={handleMouseleave} use:someAction /> -->
<a href="/head">18단계</a>

<style>
	div {
		height: 200dvh;
	}
</style>

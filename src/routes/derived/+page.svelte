<script>
	let count = $state(0);
	let doubled = $derived(count * 2);

	let count2 = $state(0);
</script>

<button class="btn" onclick={() => count++}>
	{doubled}
</button>

<button onclick={() => count2++}> 테스트:{count2}</button>

<p>{count} doubled is {doubled}</p>

<style>
	.btn {
		width: 200px;
		height: 40px;
		background-color: aqua;
	}
</style>

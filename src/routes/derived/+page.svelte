<script>
	let count = $state(0);
	let doubled = $derived(count * 2);

	let count2 = $state(0);

	let numbers = $state([1, 2, 3]);
	let total = $derived.by(() => {
		let total = 0;
		for (const n of numbers) {
			total += n;
		}
		return total;
	});
</script>

<button class="btn" onclick={() => count++}>
	{doubled}
</button>

<button onclick={() => count2++}> 테스트:{count2}</button>

<p>{count} doubled is {doubled}</p>

<button onclick={() => numbers.push(numbers.length + 1)}>
	{numbers.join(' + ')} = {total}
</button>
<a href="/effect">3단계</a>

<style>
	.btn {
		width: 200px;
		height: 40px;
		background-color: aqua;
	}
</style>

<script lang="ts">
	let boxes = [
		{ width: 200, height: 200 },
		{ width: 300, height: 300 },
		{ width: 500, height: 500 }
	];
</script>

{#each boxes as box}
	{@const area = box.width * box.height}
	<br />{box.width} * {box.height} = {area}
{/each}

@const는 로컬 상수 정의

#if ..., #each ..., #snippet ...
이 구문 안에서만 사용 가능

<a href="/debug">14단계</a>
<style>
</style>

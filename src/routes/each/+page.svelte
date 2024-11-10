<script lang="ts">
	const developer = ['나동재', '다동재', '라동재'];
	const designer: string[] = [];
</script>

<h1>each</h1>

<ul>
	{#each developer as name, index}
		<li>{index}.{name}</li>
	{/each}
</ul>

<ul>
	{#each designer as design}
		<li>{design}</li>
	{:else}
		<li>디자이너 없어</li>
	{/each}
</ul>
<a href="/key">10단계</a>
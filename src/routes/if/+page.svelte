<script lang="ts">
	let text = $state('');

	const handleValue = (e: string) => {
		return (text = e);
	};
</script>

<input type="text" value={text} oninput={(e) => handleValue(e.currentTarget.value)} />
<br />
<p>{text}</p>
<br />
{#if text && text !== 'name'}
	<p>글자 작성임</p>
{:else if text === 'name'}
	<p>이름임</p>
{:else}
	<p>빈값</p>
{/if}
<a href="/each">9단계</a>

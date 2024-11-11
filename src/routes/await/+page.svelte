<script lang="ts">
</script>

<h1>await</h1>

{#await new Promise((resolve, rejected) => setTimeout(resolve, 3000))}
	<p>로딩중...</p>
{:then}
	<p>처리성공</p>
{:catch error}
	<p>실패</p>
{/await}

{#await fetch('https://jsonplaceholder.typicode.com/posts/1').then( (response) => response.json() ) then value}
	<div>
		{value.body}
	</div>
{/await}


lazy import csr
{#await import('../../components/Button.svelte') then { default: Component }}
	<Component />
{/await}

<a href="/snippet">11단계</a>

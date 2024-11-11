<script lang="ts">
	type Img = {
		src: string;
		width: number;
		height: number;
		caption: string;
		href?: string;
	};

	let images: Img[] = [
		{
			src: 'https://picsum.photos/600/200',
			width: 600,
			height: 200,
			caption: 'this image has a link',
			href: 'https://example.com'
		},
		{
			src: 'https://picsum.photos/600/250',
			width: 600,
			height: 250,
			caption: 'this one does not'
		}
	];


	let { message = `it's great to see you!` } = $props();
</script>

<h1>photos</h1>
컴포넌트로 뺴기 싫을 때 내부에서 snippet 문법으로 공통 ui를 뺸다

{#snippet figure(image: Img)}
	<figure>
		<img src={image.src} alt={image.caption} width={image.width} height={image.height} />
		<figcaption>{image.caption}</figcaption>
	</figure>
{/snippet}

{#each images as image}
	{#if image.href}
		<a href={image.href}>
			{@render figure(image)}
		</a>
	{:else}
		{@render figure(image)}
	{/if}
{/each}


이런식으로 스코프도 가능
{#snippet hello(name: string)}
	<p>hello {name}! {message}!</p>
{/snippet}

{@render hello('alice')}
{@render hello('bob')}

<style>
	h1 {
		font-size: 2em;
	}

	figure {
		background: white;
		padding: 1em;
		margin: 0 0 1em 0;
		filter: drop-shadow(2px 4px 10px rgba(0, 0, 0, 0.1));
	}

	img {
		width: 100%;
		height: auto;
		background: #eee;
	}
</style>

<script lang="ts">
	let { options, ...props }: { options: { title: string; content: string; isOpen: boolean }[] } =
		$props();
</script>

{#each options as { title, content, isOpen }}
	<details open={isOpen} {...props}>
		<summary>{title}</summary>
		<p>{content}</p>
	</details>
{/each}

<style>
</style>

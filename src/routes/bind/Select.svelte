<script lang="ts">
	let {
		value = $bindable(),
		options,
		...props
	}: { value: string; options: { title: string; value: string }[] } = $props();
</script>

<select bind:value {...props}>
	{#each options as { title, value }}
		<option {value}>{title}</option>;
	{/each}
</select>

<style>
</style>

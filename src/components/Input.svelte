<script>
	let { value = $bindable(), ...props } = $props();
</script>
$bindable() 실시간 onChange
<input bind:value {...props} />

<style>
	input {
		font-family: 'Comic Sans MS';
		color: deeppink;
	}
</style>

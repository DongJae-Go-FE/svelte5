<script>
	import Input from '../../components/Input.svelte';

	let message = $state('hello');
</script>
실시간 바인드 즉 onChange
<Input bind:value={message} />
<p>{message}</p>

<script>
	import PropsButton from '../../components/PropsButton.svelte';

	let count = $state(0);
</script>

<PropsButton name="테스트" {count} />
<a href="/bindable">5단계</a>
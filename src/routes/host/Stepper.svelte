<svelte:options customElement="my-stepper" />
 <!-- 내부에서 컴포넌트 명 바꾺:? -->


<script lang="ts">
	function dispatch(type: string) {
		$host().dispatchEvent(new CustomEvent(type));
	}
</script>

<button onclick={() => dispatch('decrement')}>decrement</button>
<button onclick={() => dispatch('increment')}>increment</button>


커스텀 이벤트?
아니면 ref 하면서 이해 필요
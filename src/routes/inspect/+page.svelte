<script>
	let count = $state(0);
	let message = $state('hello');

	$inspect(count, message); // will console.log when `count` or `message` change

	$inspect(count).with((type, count) => {
		if (type === 'update') {
			debugger; // or `console.trace`, or whatever you want
		}
	});
</script>

<button onclick={() => count++}>Increment</button>
<input bind:value={message} />

쉽게 이해를 하면 디버깅 도구 
초기 init
업데이트 update


with과 함께 쓰면 type에 따라 디버깅 가능


1. 실시간 상태 관찰
$inspect를 사용하면 컴포넌트의 상태 변수를 실시간으로 관찰할 수 있습니다. 이는 데이터가 변경될 때마다 현재 값을 로그로 출력하므로, 개발자는 변수의 변화를 즉시 확인할 수 있습니다.
2. 디버깅 용이성
애플리케이션의 데이터 흐름이나 상태 변화를 추적하는 데 도움을 줍니다. 예상치 못한 동작이나 버그를 쉽게 찾아낼 수 있어 디버깅 과정이 훨씬 수월해집니다.
3. 반응형 이해 촉진
Svelte의 반응형 프로그래밍 모델을 이해하는 데 도움을 줍니다. $inspect를 사용함으로써 반응형 선언이 어떻게 작동하는지, 데이터가 어떻게 변하는지를 명확히 알 수 있습니다.
4. 학습 도구
Svelte를 처음 배우는 개발자에게 유용합니다. $inspect를 통해 데이터 및 상태 변화를 직관적으로 이해할 수 있어, Svelte의 반응형 개념을 더 잘 익힐 수 있습니다.
5. 개발 생산성 향상
개발 중에 상태를 빠르게 검사할 수 있어, 문제를 빠르게 해결할 수 있습니다. 이는 전체적인 개발 효율성을 높이는 데 기여합니다.
6. DevTools와의 통합
Svelte DevTools와 함께 사용할 때 더욱 강력한 도구가 됩니다. $inspect를 통해 얻은 정보는 DevTools에서 제공하는 데이터와 결합되어, 더 깊이 있는 분석을 가능하게 합니다.



<a href="/host">7단계</a>
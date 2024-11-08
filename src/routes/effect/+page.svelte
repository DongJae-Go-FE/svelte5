<script lang="ts">
	let size = $state(50);
	let color = $state('#ff3e00');

	let canvas: HTMLCanvasElement;

	$effect(() => {
		const context = canvas.getContext('2d');

		if (context) {
			context.clearRect(0, 0, canvas.width, canvas.height);

			// this will re-run whenever `color` or `size` change
			context.fillStyle = color;
			context.fillRect(0, 0, size, size);
		}
	});

	let state2 = $state({ value: 0 });
	let derived = $derived({ value: state2.value * 2 });

	// 이것은 한 번만 실행됩니다. 왜냐하면 `state`는 재할당되지 않고(단지 변형만 됩니다)
	$effect(() => {
		state2;
		console.log(state2);
	});

	// 이것은 `state.value`가 변경될 때마다 실행됩니다...
	$effect(() => {
		state2.value;
		console.log(state2.value);
	});

	// ...그리고 이것도 마찬가지입니다. 왜냐하면 `derived`는 매번 새로운 객체이기 때문입니다.
	$effect(() => {
		derived;
		console.log(derived);
	});

	//$effect 안에 있는 값을 직접 변경해야한다.

	let a = $state(false);
	let b = $state(false);

	$effect(() => {
		console.log('running');

		if (a || b) {
			console.log('inside if block');
		}
	});

	//그리고 useEffet랑 다르게 a,b 두값이 바뀌어도 작동하는게 아니라 마지막에 읽은 값에만 재반응을 한다,


	//메모리 누수 없이 	$effect안에서 동작여부 확인
	console.log('in component setup:', $effect.tracking()); // false

	$effect(() => {
		console.log('in effect:', $effect.tracking()); // true
	});


	//https://svelte.dev/docs/svelte/$effect#When-not-to-use-$effect

	//싱태값을 변경할 때는 $effect를 쓰지말고 derived를 쓸 것, $effect는 dom조작용으로만 사용
	//만약 꼭 써야 하는 경우

	// let left = {
	// 	get value() {
	// 		return total - spent;
	// 	},
	// 	set value(v) {
	// 		spent = total - v;
	// 	}
	// };
	//get set을 씁시다.
</script>

<div>effect</div>
<p>리액트 useEffect랑 비슷</p>
<p>리액트랑 다르게 자동으로 변경값 감지 디팬던시 필요 없음</p>
<p>안에서 비동기로 실행하는 함수가 있으면 그게 최우선임, 아무리 input으로 바꿔도 반응 없음</p>

<canvas bind:this={canvas} width="100" height="100"></canvas>

<button onclick={() => (state2.value += 1)}>
	{state2.value}
</button>

<p>{state2.value} doubled is {derived.value}</p>

<button onclick={() => (a = !a)}>a is {a}</button>
<button onclick={() => (b = !b)}>b is {b}</button>

<p>in template: {$effect.tracking()}</p>

<!-- true -->


<a href="/props">4단계</a>

<style>
</style>

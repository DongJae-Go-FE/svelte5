<script lang="ts">
	import type { Action } from 'svelte/action';

	const myaction: Action = (node) => {
	//use랑 함께 사용하면 $effect unmount를 할 수 있다

		$effect(() => {
			//처음 렌더링할 때

			return () => {
				// 언마운트 후
			};
		});
	};
	//처음 랜더링할 때만 사용
	//그뒤 인수가 변경해도 실행 안함
	//리액트에서 useRef + useEffect로 외부 라이브러리 넣었던 거
</script>

<h1>use</h1>


<div use:myaction>...</div>

<a href="/style">16단계</a>
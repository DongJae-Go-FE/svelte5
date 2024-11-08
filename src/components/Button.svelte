<script module> //컴포넌트 모듈 단위, 컴포넌트가 로드될 때 마다, 모든 인스턴스 즉 컴포넌트가 공유하는 자바스크립트
//rune $ 스벨트 접두사

	let message = $state('rune test'); //state 개념
	let count = $state(0);

	const handleClick = () => {
		console.log('콘솔', message);
		count++;
	};
</script>

<script>
    //컴포넌트 각각에만 즉 컴포넌트 인스턴스가 생성 될 때만
</script>

<button onclick={handleClick}>버튼 키운트 : {count}</button>

<style>
	button {
		width: 200px;
		height: 40px;

		background-color: aquamarine;
	}
</style>

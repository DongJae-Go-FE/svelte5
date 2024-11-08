<script module>
	//컴포넌트 모듈 단위, 컴포넌트가 로드될 때 마다, 모든 인스턴스 즉 컴포넌트가 공유하는 자바스크립트
	//rune $ 스벨트 접두사
</script>

<script lang="ts">
	let { name, count }: { name: string; count: number } = $props();

	const handleClick = () => {
		return console.log((count += 1));
	};
</script>

<button onclick={handleClick}>{name}</button>

<style>
	button {
		width: 200px;
		height: 40px;

		background-color: aquamarine;
	}
</style>

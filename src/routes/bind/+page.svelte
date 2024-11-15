<script lang="ts">
	import Input from './Input.svelte';
	import Select from './Select.svelte';
	import Details from './Details.svelte';
	import PropsButtonRender from '../../components/PropsButtonRender.svelte';

	let inputValue = $state('');

	let selectValue = $state('');
	let options = [
		{ title: '전체', value: '' },
		{ title: '1', value: '1' },
		{ title: '2', value: '2' }
	];

	let options2 = [
		{ title: '1', content: '1', isOpen: false },
		{ title: '2', content: '2', isOpen: false },
		{ title: '3', content: '3', isOpen: false }
	];

	let html = $state(`<div>테스트1</div>`);

	// let width;
	// let height;
	// console.log(width, height);

	/** @type {HTMLCanvasElement} */
	// let canvas;

	// $effect(() => {
	// 	const ctx = canvas.getContext('2d');
	// 	drawStuff(ctx);
	// });
</script>

props는 보통 부모에서 자식으로 밖에 불가능하지만<br /> :bind를 사용하여 자식에서 부모로 보내는
양뱡향 통신이 가능하고 <br />$bindable를 사용해서 실시간으로 자식에서 부모 상태를 변경도 가능하다
<br />
<br />
<Input bind:value={inputValue} />
<br />{inputValue}

<br />
<Select bind:value={selectValue} {options} />
<br />{selectValue}

<br />
<Details options={options2} />

<PropsButtonRender>테스트</PropsButtonRender>

<div contenteditable="true" bind:innerHTML={html}></div>

<!-- <div class="box" bind:offsetWidth={width} bind:offsetHeight={height}></div> -->

<!-- <canvas bind:this={canvas} /> -->

<style>
	/* .box {
		background-color: red;
		width: 100px;
		height: 100px;
	} */
</style>

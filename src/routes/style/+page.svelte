<script lang="ts">
</script>

<h1>style</h1>

<a href="/">17단계</a>
이런 방식 style:background="red"
<div style:background="red"></div>
<br />
기존방식
<div style="background: blue;"></div>
<br />
important
<p class="test" style:background|important="pink">테스트</p>
<br />
<div style="color: blue;" style:color="red">This will be red</div>
지시어가 먼저


<a href="/window">17단계</a>
<style>
	.test {
		width: 200px;
		height: 200px;

		background-color: bisque;
	}

	div {
		width: 200px;
		height: 200px;
	}
	/* 전역으로 가능 */
	:global(body) {
		padding: 0;
		margin: 0;

		background-color: yellow;
	}
</style>

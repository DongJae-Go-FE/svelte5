<script lang="ts">
</script>

<article>
	{@html `<div class="box">html 삽입</div>`}
	위처럼 삽입
</article>

XSS 공격을 방지하기 위해 전달된 문자열을 이스케이프하거나 제어할 수 있는 값으로만 ​​채우십시오 . 정제되지 않은 콘텐츠를 렌더링하지 마십시오.

<a href="/const">13단계</a>

<style>
	/* 이렇게 :global 없으면 @html의 css의 미적용 */
	article :global {
		div {
			width: 200px;
			height: 200px;
			background-color: red;
		}
	}
</style>

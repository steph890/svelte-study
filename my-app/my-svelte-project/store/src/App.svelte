<script>
	// 꺼내기
	import { count, power, elapsed } from "./store.js";
	import Increase from "./Increase.svelte";	// count 증가 기능 컴포넌트
	import Decrease from "./Decrease.svelte";	// count 감소 기능 컴포넌트


	// 5. time 추가
	import Time from "./Time.svelte";

	// 6. flag 변수 생성: 하위 템플릿 생성을 결정함
	let flag1 = false;
	let flag2 = false;
</script>

<main>
	<section>
		<h2> count는 {$count} 입니다. </h2>
		<input type=range bind:value={$count} step=1 min=1 max=100>
	</section>
	<section> <!-- 감소 / 증가 버튼 인스턴스 생성-->
		<Decrease/><Increase/>
	</section>

	<!-- 7. time 표시하기 -->
	<section>
		<br>
		<!-- 8. 템플릿 생성 결정 -->
		<input type="checkbox" bind:checked={flag1}> 시간표시 1
		{#if flag1} <!-- 체크 여부에 따라 Time 컴포넌트 토글 -->
			<Time/>
		{/if}
		<br>
		<input type="checkbox" bind:checked={flag2}> 시간표시 2
		{#if flag2} <!-- 체크 여부에 따라 Time 컴포넌트 토글 -->
			<Time/>
		{/if}
	</section>

	<!-- 2. 사용하기 -->
	<h1>{$count}^2 = {$power}입니다. </h1>
	<h1>접속 후 {$elapsed}초가 지났습니다. </h1>
</main>

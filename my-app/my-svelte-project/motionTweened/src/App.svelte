<script>
	// tweened 사용 선언
	import { tweened } from "svelte/motion";

	// tweened를 통하여 progress 스토어 생성, duration 옵션 사용
	const progress = tweened(0, { duration: 1000 });

	// 스토어의 값이 변하는 추이를 보기 위해 콘솔에 출력
	progress.subscribe(v=>console.log(v));
</script>

<style>
	progress { width: 100% }

</style>

<progress value={$progress}></progress>
<button on:click="{() => progress.set(0.5)}">50%</button>
<button on:click="{() => progress.set(1)}">100%</button>

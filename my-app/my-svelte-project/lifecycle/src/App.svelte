<script>
	// Child 컴포넌트 임포트
	import Child from "./Child.svelte";
	let flag=false;
</script>

<section>
	<button on:click={()=> { flag =! flag }}> <!-- 클릭할 때마다 flag 값을 토글 -->
		{flag==true?"Destroy Child!":"Create Child!"}
	</button>

	<p>
		{#if flag} <!-- flag 값에 따라 Child 컴포넌트 생성/파괴 -->
			<Child/>
		{/if}
	</p>
</section>
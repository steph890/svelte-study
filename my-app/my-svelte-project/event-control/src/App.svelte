<script>
	let count = 0
	const search = (event)=>{
		console.log(event.target);
		count = count + 1;
	}
	const increase = ()=>{
		console.log("increase : 조회 버튼 클릭~!");
		count = count + 1;
	}
</script>

<!-- button on:click={search} on:click={increase}-->
<button on:click={search}>
	Search ({count})
</button>


<!-- 인라인으로 이벤트 처리하기 -->
<button on:click={(event)=>{
	console.log(event.target);
	count=count +1;
}}>
Search Inline ({count})
</button>

<!-- 이벤트 제한자 사용하기 -->
<button on:click|once={search}> <!-- 한번만 호출되는 once -->
	Search Once ({count})
</button>
<script>
    import { goto } from "$app/navigation";    // 화면 이동을 위한 goto 함수 사용 선언
    import { scoreList } from "$lib/store.js";   // 점수 목록을 가져오기 위한 scoreList 함수 사용 선언
</script>

<svelte:head>
    <title>Brain Color</title>
</svelte:head>



<h1 style="text-align:center;">두뇌 개발 게임</h1>

<h3 style="text-align:center;">이번 주의 점수</h3>
<table style="width:100%;">
    <thead>
        <tr>
            <th>NO</th>
            <th>점수</th>
            <th>이름</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td style="text-align:center;">============</td>
            <td style="text-align:center;">============</td>
            <td style="text-align:center;">============</td>
        </tr>
  
        {#each $scoreList as item ,index}
            <tr>
                <td style="text-align:center;">{index + 1}</td>
                <td style="text-align:center;">{item.score}</td>
                <td style="text-align:center;">{item.name}</td>
            </tr>
        {/each}
    </tbody>
</table>



<p style="text-align:center;">
    <button style="width:100%;height:60px;font-weight:bold;font-size:30px"
      on:click={()=>{
        goto("/quiz");
      }}
    >게임하기</button>
</p>
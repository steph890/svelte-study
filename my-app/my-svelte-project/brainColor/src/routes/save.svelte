<script>
    import { goto } from "$app/navigation";           // 화면 이동을 위한 goto 함수 사용 선언
    import { score, scoreList } from "$lib/store.js"; // 스토어 변수 사용 선언

    let name = "--";

    function saveScore(){
    $scoreList.push({ score: $score, name: name });
    $scoreList.sort((a, b) => {return b.score - a.score});

    $scoreList.pop();

    goto("/");
    }
</script>

<svelte:head>
    <title>점수 저장하기</title>
</svelte:head>

<h1 style="text-align:center;">점수 저장하기</h1>

<h4>이름을 입력하고 저장 버튼을 누르세요</h4>

<p>획득점수: {$score}</p>

<p>이름: <input type="text" bind:value={name} /></p>

<button on:click={saveScore}> 저장 </button>

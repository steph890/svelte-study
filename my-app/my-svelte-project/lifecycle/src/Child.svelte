<script>
    // 테스트용 input 박스에 포커스 주기
    // -> 삭제함 document.getElementById("text01").focus();

    let txt;

    // svelte 컴포넌트 임포트, 라이프사이클 함수 4종 꺼내기
    import { onMount, beforeUpdate, afterUpdate, onDestroy } from "svelte";

    // onMount 예제 코드
    onMount(()=> {
        txt = document.getElementById("text01");    // 돔에서 엘리먼트 찾아오기
        txt.focus(); // 포커스 추가
        console.log("Child onMount 호출됨");
    });
</script>

<h1> Child </h1>
<input type="text" id="text01"/> <!-- 테스트용 input 박스 -->
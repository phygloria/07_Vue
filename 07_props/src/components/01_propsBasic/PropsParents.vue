<script setup>
    //뷰3 문법. 셋업 한줄표현가능(위)
    import { provide, ref, readonly } from "vue";
    import PropsChild from './PropsChild.vue'
    import DarkMode from "./DarkMode.vue";
    import ReadProps from "./ReadProps.vue";

    const message = ref("hello");
    const darkState = ref(false);
    const readValue = ref("vue는 재미있다.");


    function darkMode() {
        darkState.value = !darkState.value;
        // 켜져있으면 꺼주고, 꺼져있으면 켜주는 상태. ! 부정연산자 때문에 가능.
    }

//공급자
    // provide("data", {message, darkMode});
    // {중괄호는 객체}, [대괄호는 배열] 소괄호는 함수 혹은 값을 받는 곳.
    provide("message", message);
    provide("darkMode", darkMode);
    provide("darkState", darkState);
    provide("readValue", readonly(readValue));

    provide("childDark", readonly(darkState));
    // readonly는 다른곳에서의 조작을 막아두고 원하는 곳에서만 조작가능하게 만들 때 사용.
</script>


<!-- 
    prop
    부모에서 자식 컴포넌트로 데이터를 전달하는 경우 우리는 다양한 <slot>이용할 수 있었다.
    하지만 slot의 경우 콘텐츠를 전달하기 위해 사용하는 것으로 단일 데이터를 전달하는 경우 맞지 않으며
    부모에게 전달 받은 데이터를 전달하여 '조작'하는데 어려움이 있다. //slot
    이러한 경우 우리는 데이터만 전달하기 위한 용도로 props를 사용할 수 있다. //props :데이터 받아서 자식컴포넌트에서 재이벤트 가능.
    -->
<template>
    <div :class="{container:true, dark:darkState}"> 
    <!-- 클래스는 css속성 묶음 -->
    props 입력 <input v-model="message"/>

    </div>
    <PropsChild/>
    <br>
    <DarkMode/>
    <ReadProps/>
</template>

<style scoped>
.container{
    border :  1px solid;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.dark{
    background-color: black;
    color: aliceblue;
}
</style>
<script setup>
import {onMounted, ref} from 'vue';
import {useRoute} from 'vue-router';
//url 리소스를 가져올 수 있게 해주는 객체

const route = useRoute();

onMounted(()=>{
    console.log(route.params);
})
</script>

<template>
    <h1>PathVariable : {{ $route.params.id }}</h1>
</template>
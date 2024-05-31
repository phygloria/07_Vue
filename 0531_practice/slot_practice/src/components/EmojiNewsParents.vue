<script setup>
    import {ref} from 'vue';
    import EmojiNewsChild from './EmojiNewsChild.vue';

    const EmojiName = ref("");
    // const emoji = ref("");
    // const emojis = reactive({});

</script>


<template>
    <div>
        <h1>홍길동 동서남북 소환 : </h1>
        <input v-model="EmojiName"/> 
        <EmojiNewsChild>
            <template #[EmojiName]>
                {{ EmojiName.img }}
                <img class="img"  src="https://i.pinimg.com/564x/b2/0e/39/b20e393c1ea3aea94537de3f47a16400.jpg"/>
            </template>            
        </EmojiNewsChild>
    </div>
      
</template>

<style scoped>
.img{
    width: 200px; height: 200px;
}
    .parentsContainer{
        /* display: flex; */
        align-items: center;
        flex-direction: column;
        width: 200px;
        height: 200px;
        border: 1px solid;  
         
    }
    

</style>
<template>
    <a-row>
        <a-col :span = "21">
            <a-input 
                v-model:value = "inputVal" 
                placeholder="请输入消息内容" 
                @keyup.enter="handleSend">
            </a-input>
        </a-col>
        <a-col :span="3">
            <a-button
                type="primary"
                @click="handleSend"
                style="width: 100%; padding :2px"    
            >发送</a-button>
        </a-col>
    </a-row>
</template>

<script setup>
import { ref,defineEmits } from 'vue';

const emits = defineEmits(["send"]);

const inputVal = ref("");

const handleSend = () =>{
    emits("send",inputVal.value);
    inputVal.value = "";
}

</script>

<style scoped>

</style>
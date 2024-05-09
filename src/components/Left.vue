<template>
    <a-row>
        <a-col :span = "2">
            <img src ="/src/assets/3.jpg" width="100%" style="padding: 3px">
        </a-col>
        <a-col :span = "20" style="padding: 5px">
            <div class="chat">{{props.message}}</div>
        </a-col>
    </a-row>
</template>

<script setup>
const props = defineProps(['message']);
</script>

<style scoped>
.chat{
    width: fit-content;
    height: 100%;
    background: white;
    border-radius: 8px;
    line-height: 55px;
    font-size: 18px;
    padding-left: 8px;
    padding-right: 8px;
    color: black;
}
</style>
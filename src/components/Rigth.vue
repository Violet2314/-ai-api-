<!--offset表示左移两格  -->
<template>
    <a-row>
        <a-col :span = "20" style="padding: 5px" :offset = "2">
            <a-flex justify="flex-end">
                <div class="chat">{{props.message}}</div>
            </a-flex>
        </a-col>
        <a-col :span = "2">
            <img src ="/src/assets/2.jpg" width="100%" style="padding: 3px"/>
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
    background: #2cdc2c;
    border-radius: 8px;
    line-height: 55px;
    font-size: 18px;
    padding-left: 8px;
    padding-right: 8px;
    color: black;
}
</style>
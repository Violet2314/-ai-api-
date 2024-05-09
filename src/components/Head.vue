<template>
  <a-row class="wok">
    <a-col :span="2" @click="message.info('点击了返回按钮')">
        <a-flex
            justify="center"
            align="center"
            style="font-size: 24px; height: 100%"
        >
            <LeftOutlined />
        </a-flex>
    </a-col>
    <a-col :span="20">
        <a-flex justify="center" style="font-size: 24px"> Man! </a-flex>
    </a-col>
    <a-col :span="2" @click="message.info('点击了菜单按钮')">
        <a-flex
            justify="center"
            align="center"
            style="font-size: 24px; height: 100%"
        >
            <EllipsisOutlined />
        </a-flex>
    </a-col>
  </a-row>
</template>

<script setup>
import { message } from "ant-design-vue";
import {LeftOutlined,EllipsisOutlined} from "@ant-design/icons-vue"
</script>

<style scoped>
.wok{
    line-height: 56px;
    background: #ebe7e7;
    border-bottom: solid 1px black;
}
</style>
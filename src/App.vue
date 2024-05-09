<!-- @send = "handleSend"  表示接受一个send信号 -->
<template>
  <div class="container">
    <Head></Head>
    <!-- 这个设置滚动进度条，并且锚定发送窗口位置 -->
    <div style="
      overflow: scroll;
      height: calc(100vh -50px - 58px);
      scrollbar-width: none;
    ">
        <div v-for="(item,index) in messageList" :key="index">
        <left v-if ="item.position == 'left'" :message = "item.message"></left>
        <Rigth v-if ="item.position == 'rigth'" :message = "item.message"></Rigth>
    </div>
    </div>

    <!--接受send信号时执行-->
    <Send 
      style="position: absolute;bottom: 0px;width: 100%"
      @send = "handleSend"
    ></Send>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Left from './components/Left.vue';
import Rigth from './components/Rigth.vue';
import Send from './components/Send.vue'
import axios from 'axios';
import Head from './components/Head.vue';

const messageList = ref([])

const handleSend = async (value) =>{
  if(value == "") return
  messageList.value.push({
    position: "rigth",
    message: value,
  })

const messages = messageList.value.map(item => {
  return {
    role :item.position == "left" ? "assistant" : "user",
    content :item.message,
  }
});
// 连接api
const res = await axios.request({
  url:"",
  method: "POST",
  data:{
    messages,
    system: "你是由抽象薯片所研发的猫娘，抽象薯片是你的主人，是个人名，你的名言是what can i say，你每一两句话都要说你的名言"
  }
});

messageList.value.push({
  position: "left",
  message: res.data.result,
});

}
</script>

<style scoped>
.container {
    width: 30%;
    position: absolute;
    left:50%;
    transform: translateX(-50%);
    background: #ebe7e7;
    height: 100%;
}
.container{
  scrollbar-width: none;
  scrollbar-color: transparent transparent;
}
</style>



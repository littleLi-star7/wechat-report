<template>
  <div>
    <div class="a">
      一年中 总有几个特殊的日子 <span class="value">{{ content.length }}</span
      >
    </div>
    <div class="b">
      你在2023.10.10提交了最多次数的任务
    </div>
    <div class="b value">
      300次
    </div>
    <div class="c">...</div>
    <div class="b">
      <span class="value">2023.6.18 </span>
      你睡得很晚
    </div>
    <div class="b ">
      <span class="value">23:56:17 </span>
      还在提交任务，还记得那天在做什么吗
    </div>    
    <div class="d">
      {{ new Date() }}
    </div>
  </div>
</template>

<script>
import { longMsg } from "@/data.json";
export default {
  data() {
    return {
      ...longMsg,
    };
  },
};
</script>

<style scoped>
.a {
  font-size: 5vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.b {
  padding-top: 5vh;
  white-space: normal;
  text-overflow: ellipsis;
  overflow: hidden;
  line-height: 2;
  color: ebf45f;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.d {
  text-align: right;
  padding-top: 3vh;
  font-weight: bolder;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1.5s;
  animation-fill-mode: backwards;
}
</style>
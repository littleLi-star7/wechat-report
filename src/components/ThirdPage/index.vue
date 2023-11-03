<template>
  <div>
    <div class="a">
      今年你与平台共度了
      <span class="value"> {{ count }} </span>
      天
    </div>
    <div class="a">
      提交了
      <span class="value"> {{ count }} </span>
      任务
    </div>
    <div class="b">
      提交了
      <span class="value"> {{ imgCount }} </span>
      &nbsp; 任务总时长
      <span class="value"> {{ voiceCount }} </span>
      分钟
    </div>
  </div>
</template>

<script>
import data from "@/data.json";
export default {
  data() {
    return {
      ...data,
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
  animation-delay: .5s;
  animation-fill-mode: backwards;
}
.b{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2s;
  animation-fill-mode: backwards;
}
.d {
  padding-top: 10vh;
  font-size: 5vw;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2.5s;
  animation-fill-mode: backwards;
}

</style>
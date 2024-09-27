<script setup lang="ts">
import TestComponent from './components/TestComponent.vue';
import { computed } from 'vue';

let X = 200;
let rotationAngle = 45; // 新增：定义旋转角度

// 计算调整后的 margin-left
const adjustedMarginLeft = computed(() => {
  // 将角度转换为弧度
  const radians = (rotationAngle * Math.PI) / 180;
  // 计算调整后的 margin-left
  return X / Math.cos(radians);
});
</script>

<template>
  <div class="main">
    <TestComponent :rotationAngle="rotationAngle" />
    <TestComponent :marginLeft="adjustedMarginLeft" :rotationAngle="rotationAngle" />
  </div>
</template>

<style scoped>
.main {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>

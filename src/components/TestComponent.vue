<script setup lang="ts">
defineProps<{
  marginLeft?: number;
  rotationAngle: number;
}>();
</script>

<template>
  <div class="test"
    :style="{ marginLeft: marginLeft ? `${marginLeft}px` : undefined, transform: `rotate(${rotationAngle}deg)` }">
    <div class="test-content"></div>
  </div>
</template>

<style scoped>
.test {
  width: 100px;
  border: 1px solid #000;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.test-content {
  width: 50px;
  height: 100%;
  background-color: #3498db;
}
</style>

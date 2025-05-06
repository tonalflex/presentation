<template>
  <div class="arrow-container" :style="[positionStyle, { height }]">
    <div class="arrow-head" />
  </div>
</template>

<script setup lang="ts">
import type { CSSProperties } from "vue";

const props = defineProps<{
  top?: string;
  left?: string;
  right?: string;
  bottom?: string;
  height?: string; // e.g. '100px', '10rem'
}>();

const positionStyle: CSSProperties = {
  position: "absolute",
  top: props.top ?? "auto",
  bottom: props.bottom ?? "auto",
  left: props.left ?? "auto",
  right: props.right ?? "auto",
};

const height = props.height ?? "100px"; // default arrow length
</script>

<style scoped>
.arrow-container {
  width: 0;
  border-left: 2px solid gray;
}

.arrow-head {
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 0;
  border-left: 6px solid transparent;
  border-right: 6px solid transparent;
  border-top: 10px solid gray;
}
</style>

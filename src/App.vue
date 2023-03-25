<script setup>
import { ref } from "vue";

const targetElement = ref(null);
const positionInformation = ref(null);

const showPosition = () => {
  const {
    top,
    right,
    bottom,
    left,
  } = targetElement.value.getBoundingClientRect();
  positionInformation.value = `Position: Top: ${top}, Right: ${right}, Bottom: ${bottom}, Left: ${left}`;
};
</script>

<template>
  <div>
    <div ref="targetElement" class="show-position" @click="showPosition">
      Show position
    </div>
    <div>
      {{ positionInformation }}
    </div>
  </div>
</template>

<style>
.show-position {
  background-color: green;
  color: white;
  padding: 10px;
  cursor: pointer;
}
</style>

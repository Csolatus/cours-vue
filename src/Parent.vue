<script setup lang="ts">
import { ref } from "vue";
import Child from "./Child.vue";

type Operation = "increment" | "decrement";

const counter = ref<number>(0);

const handleCounterUpdate = (payload: {
  operation: Operation;
  step: number;
}) => {
  if (payload.operation === "increment") {
    counter.value += payload.step;
  } else {
    counter.value -= payload.step;
  }
};
</script>

<template>
  <div class="parent-component">
    <div class="counter-display">
      <h1>{{ counter }}</h1>
      <p>Valeur actuelle</p>
    </div>

    <Child @update="handleCounterUpdate" />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

type Operation = "increment" | "decrement";

const emit = defineEmits<{
  update: [{ operation: Operation; step: number }];
}>();

const step = ref<number>(1);
const operation = ref<Operation>("increment");

const handleClick = () => {
  emit("update", {
    operation: operation.value,
    step: step.value,
  });
};
</script>

<template>
  <div class="child-component">
    <h3>Contrôle du compteur</h3>

    <div class="field">
      <label for="step">Pas d'incrément/décrément:</label>
      <input id="step" type="number" v-model.number="step" min="1" step="1" />
    </div>

    <div class="field radios">
      <label>
        <input type="radio" value="increment" v-model="operation" />
        Incrémenter
      </label>
      <label>
        <input type="radio" value="decrement" v-model="operation" />
        Décrémenter
      </label>
    </div>

    <button
      @click="handleClick"
      :class="{
        increment: operation === 'increment',
        decrement: operation === 'decrement',
      }"
    >
      {{ operation === "increment" ? "+" : "-" }}
    </button>
  </div>
</template>
<script setup>
const props = defineProps({
  Label: {
    type: String,
    required: true
  },
  Level: {
    type: String,
    required: true,
    validator: (value) => ['normal', 'warning', 'error'].includes(value.toLowerCase())
  }
})
</script>

<template>
  <div :class="['message', `message--${Level.toLowerCase()}`]">
    <p>{{ Label }}</p>
  </div>
</template>

<style scoped>
.message {
  padding: 1rem;
  border-radius: 4px;
  margin: 1rem 0;
}

.message p {
  margin: 0;
  font-weight: 500;
}

.message--normal {
  color: #000000;
  background-color: #f5f5f5;
  border-left: 4px solid #000000;
}

.message--warning {
  color: #ff6600;
  background-color: #fff4e6;
  border-left: 4px solid #ff6600;
}

.message--error {
  color: #cc0000;
  background-color: #ffe6e6;
  border-left: 4px solid #cc0000;
}
</style>
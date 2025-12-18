<script setup>
import { inject } from 'vue';

// 3.b.i : Récupération du prénom via INJECT
const nameFromInject = inject('familyFirstName');
</script>

<template>
  <div class="box son">
    <h4>👶 Son</h4>
    
    <p>Je reçois du Grand-Père : <strong>{{ nameFromInject }}</strong></p>
  </div>
</template>

<style scoped>
.box {
  border: 2px solid #d35400;
  padding: 20px;
  margin: 10px;
  border-radius: 8px;
}
.son { background-color: #fff5eb; }
</style>
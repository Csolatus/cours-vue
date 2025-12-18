<script setup>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';

const message = ref('Tic');
let timerId = null;



onBeforeMount(() => {
  console.log('1. [TicTac] onBeforeMount : Le composant va être monté.');
});

onMounted(() => {
  console.log('2. [TicTac] onMounted : Le composant est monté dans le DOM.');
  
  // Démarrage du cycle Tic/Tac
  timerId = setInterval(() => {
    message.value = message.value === 'Tic' ? 'Tac' : 'Tic';
    console.log(`Cycle en cours... Affichage : ${message.value}`);
  }, 1000);
});

onBeforeUpdate(() => {
  console.log('3. [TicTac] onBeforeUpdate : Une donnée réactive a changé, le DOM va se mettre à jour.');
});

onUpdated(() => {
  console.log('4. [TicTac] onUpdated : Le DOM a été mis à jour.');
});

onBeforeUnmount(() => {
  console.log('5. [TicTac] onBeforeUnmount : Le composant va être détruit.');
});

onUnmounted(() => {
  console.log('6. [TicTac] onUnmounted : Le composant est détruit.');
  // NOTE : Je laisse volontairement le "bug" ici pour l'analyse (pas de nettoyage du timer)
});
</script>

<template>
  <div class="tictac-box">
    <h3>Composant TicTac</h3>
    <p class="message">{{ message }}</p>
  </div>
</template>

<style scoped>
.tictac-box {
  border: 2px dashed #42b983;
  padding: 20px;
  margin-top: 10px;
  text-align: center;
}
.message {
  font-size: 2em;
  font-weight: bold;
}
</style>
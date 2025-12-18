<script setup>
import { ref, provide } from 'vue';
import Father from './Father.vue';

// 1.b.i : Gérer le prénom de manière réactive
const firstName = ref('');

// 1.b.ii : Fournir le prénom aux composants enfants (Provide)
// On passe la ref elle-même pour conserver la réactivité partout
provide('familyFirstName', firstName);
</script>

<template>
  <div class="box grandfather">
    <h2>👴 GrandFather</h2>
    
    <label>Saisissez un prénom : </label>
    <input v-model="firstName" placeholder="Entrez un nom..." />

    <hr />

    <Father :nameFromProp="firstName" />
  </div>
</template>

<style scoped>
.box {
  border: 2px solid #2c3e50;
  padding: 20px;
  margin: 10px;
  border-radius: 8px;
}
.grandfather { background-color: #eef2f5; }
</style>
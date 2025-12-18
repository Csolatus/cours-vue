<script setup>
import { inject } from 'vue';
import Son from './Son.vue';

// 2.b.i : Récupération via PROPS
const props = defineProps({
  nameFromProp: String
});

// 2.b.i : Récupération via INJECT
// On injecte la clé définie dans le GrandFather
const nameFromInject = inject('familyFirstName');
</script>

<template>
  <div class="box father">
    <h3>👨 Father</h3>
    
    <p>Via Props (direct) : <strong>{{ nameFromProp }}</strong></p>
    
    <p>Via Inject (global) : <strong>{{ nameFromInject }}</strong></p>

    <hr />

    <Son />
  </div>
</template>

<style scoped>
.box {
  border: 2px solid #42b983;
  padding: 20px;
  margin: 10px;
  border-radius: 8px;
}
.father { background-color: #e6fff2; }
</style>
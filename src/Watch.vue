<script setup>
import { ref, reactive, watch } from 'vue'

const prenom = ref('')
const nom = reactive('')

watch(
    ()=>nom,
    (newValue, oldValue) => {
    }
)

watch(prenom, () => {
})


</script>

<template>
    <form>
        <input v-model="prenom" placeholder="Prénom"></input>
        <input v-model="nom" placeholder="Nom"></input>
    </form>
    <br>
    <h1>Bonjour {{ prenom }} {{ nom }}</h1>
</template>
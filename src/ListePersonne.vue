<script setup>
    import { ref } from 'vue';

        const personnes = ref([]);

        const PRENOMS = ["Lucas", "Lam", "Thomas sous veste", "Walide", "Matthieu", "Michel", "Melina", "Franchement", "Nuit", "Conseil"];

        function createPersonne() {
            for (let i = 0; i < 10; i++) {
                let age = Math.floor(Math.random() * 99) +1;
                let personne = {id: i, prenom: PRENOMS[i], age: age}
                personnes.value.push(personne)
            }
        }
createPersonne()
</script>

<template>
        <li v-for="personne in personnes" :key="personne.id">
            <div v-if="personne.age < 18" class="blue"> {{ personne.prenom }} / {{ personne.age }}</div>
            <div v-else class="default">{{ personne.prenom }} / {{ personne.age }}</div>
        </li>
</template>

<style scoped>
    .default {
        color: black
    }

    .blue {
        color: blue
    }
</style>
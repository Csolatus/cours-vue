<script setup>
import { ref, computed } from 'vue';

const note1 = ref(0);
const note2 = ref(0);
const note3 = ref(0);

const somme = computed(
    ()=> parseInt(note1.value) + parseInt(note2.value) +  parseInt(note3.value)
);

</script>

<template>
    <form>
        <input v-bind:value="note1" @input="event => note1 = event.target.value">
        </input>

        <input v-bind:value="note2" @input="event => note2 = event.target.value">
        </input>
            
        <input v-bind:value="note3" @input="event => note3 = event.target.value">
        </input>
    </form>

    <span>Somme calculée : {{ somme }} </span>
</template>


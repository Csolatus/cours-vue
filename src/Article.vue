<script setup>
import { useSlots } from 'vue';
const slots = useSlots();
</script>

<template>
    <BaseSlot>
        <p>Ceci est l'article de base</p>
        <em>Auteur</em>
    </BaseSlot>
    <div>
        <h1>
            <slot></slot>
        </h1>
    </div>
</template>

<style scoped>

</style>
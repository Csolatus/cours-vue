<script setup>
import React from './React.vue'
import Somme from './Somme.vue'
import Watch from './Watch.vue'
import Message from './Message.vue'
</script>

<template>
  <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>

  <React></React>
  <br>
  <Somme></Somme>
  <br>
  <br>
  <Watch></Watch>
  <br>
  <Message Label="Ceci est un message normal" Level="normal"/>
  <Message Label="Ceci est un message d'avertissement" Level="warning"/>
  <Message Label="Ceci est un message d'erreur" Level="error"/>
</template>

<style scoped></style>

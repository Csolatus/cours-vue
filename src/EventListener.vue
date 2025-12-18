<script setup>
import { ref } from 'vue';

const lastKeyPressed = ref('');

const handleKeyLogger = (event) => {
  lastKeyPressed.value = event.key;
};

const textColor = ref('black');

const clickCount = ref(0);

const handleLinkClick = () => {
  alert("Redirection bloquée ! L'alerte s'affiche à la place.");
};

const handleFormSubmit = () => {
  console.log("Soumission du formulaire empêchée (prevent default).");
};
</script>

<template>
  <div class="listener-container">
    <h2>Démonstration des Événements Vue.js</h2>

    <section>
      <h3>A. Formulaire (Prevent Default)</h3>
      <form action="./postData.php" @submit.prevent="handleFormSubmit">
        <button type="submit">Soumettre le formulaire</button>
      </form>
    </section>

    <hr />

    <section>
      <h3>B. Keylogger</h3>
      <input 
        type="text" 
        placeholder="Tapez ici..." 
        @keydown="handleKeyLogger" 
      />
      <p>Dernière touche appuyée : <strong>{{ lastKeyPressed }}</strong></p>
    </section>

    <hr />

    <section>
      <h3>C. Effet de survol (MouseOver/Out)</h3>
      <p 
        @mouseover="textColor = 'blue'" 
        @mouseout="textColor = 'black'"
        :style="{ color: textColor, cursor: 'pointer', fontWeight: 'bold' }"
      >
        Passez la souris sur ce texte pour changer sa couleur.
      </p>
    </section>

    <hr />

    <section>
      <h3>D. Compteur de clics</h3>
      <button @click="clickCount++">Cliquez-moi</button>
      <p>Nombre de clics : {{ clickCount }}</p>
    </section>

    <hr />

    <section>
      <h3>E. Lien bloqué</h3>
      <a href="./nextPage.html" @click.prevent="handleLinkClick">
        Aller vers NextPage (Bloqué)
      </a>
    </section>
  </div>
</template>

<style scoped>
.listener-container {
  font-family: sans-serif;
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
}
section {
  margin-bottom: 15px;
}
button {
  cursor: pointer;
  padding: 5px 10px;
}
</style>
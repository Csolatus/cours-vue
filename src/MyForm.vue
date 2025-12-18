<script setup>

</script>

<template>
    <label for="firstnameID">Prénom</label>
    <input type="text" placeholder="Prénom" v-model="formData.firstname"/>
    <br></br>
    <label for="lastnameID">Nom</label>
    <input type="text" placeholder="Nom" v-model="formData.lastname"></input>
    <br></br>
    <input type="text" placeholder="Email" v-model="email">
    <br></br>
    <input type="number" placeholder="Nombre Personnes" min="1" max="5" v-model="nombrePersonne">
    <br></br>
    <div>
        Destination : 
        <select type="select" placeholder="Destination" v-model="destination">
            <option>France</option>
            <option>Espagne</option>
            <option>Corée</option>
            <option>Perpignan</option>
            <option>Villejuif</option>
            <option>Finale</option>
        </select>
    </div>
    <br></br>
    <input type="date" placeholder="Date">
    <br></br>
    <div>
        <input type="checkbox" id="dateRetour">
        Date Retour ?
    </div>
    
</template>

<style scoped>

</style>
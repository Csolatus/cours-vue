<script setup>
    import { ref } from 'vue' 
    const props = [
        {title : "titre 1", url : "https://picsum.photos/200/300"},
        {title : "titre 2", url : "https://picsum.photos/200"},
        {title : "titre 3", url : "https://picsum.photos/200/400"}
    ]

    const indexActuel = ref(0)

    function getTitle(indexActuel) {
        return props[indexActuel.value].title
    }

    function getUrl(indexActuel) {
        return props[indexActuel.value].url
    }

    function suivant() {
        indexActuel.value++;

        if (indexActuel.value >= props.length){
            indexActuel.value = 0
        }
    }

    function precedent() {
        indexActuel.value--;

        if (indexActuel.value < 0){
            indexActuel.value = 0
        }
    let slideshow;
    let isInPlay = false;
    function playPause() {
        if (isInPlay){
        slideshow = setInterval(() => {
            next()
        }, 500);
        isInPlay = true;
    }
     else {  
        clearInterval(slideshow);
        isInPlay = false;
     }
    }

    }

</script>

<template>
    <div class="caroussel">
        <h1>{{ props[indexActuel].title }}</h1>
        <div class="images">
            <button @click="precedent()">precedent</button>
            <img :src="props[indexActuel].url">
            <button @click="suivant()">suivant</button>
            <button @click="playPause()">play/pause</button>
        </div>
    </div>

</template>

<style scoped>

</style>
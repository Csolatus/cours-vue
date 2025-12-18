<script setup>
    function getRandomClass() {
        const randomNumber = parseInt(Math.random() * 3);
    switch(randomNumber) {
        case 0: return "bleu";
        case 1: return "rouge";
        case 2: return "vert";
        }
    }

    const URLs = [
        'https://www.efrei.fr',
        'https://fr.vuejs.org',
        'https://developer.mozilla.org/en-US/',
    ]

    const getUrl = () => {
        return "https://picsum.photos/200/300"
    }

    const getImage = () => {
        return "https://picsum.photos/200/300"
    }

    const getStyle = () => {
        return "color: violet"
    }

</script>

<template>
    <div class="bleu">salam</div>
    <div v-bind:class="getRandomClass()">salam 2</div>
    <div :class="getRandomClass()">salam 3</div>
    <a :href="getUrl()">salam 4</a>
    <p v-bind:style="getStyle()">texte</p>
    <img :src="getImage()"></img>
</template>

<style>
    .bleu {
        color :blue
    }

    .rouge {
        color :red
    }

    .vert {
        color :green
    }
</style>
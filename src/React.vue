
<script setup>
import{ ref } from 'vue'
import{ reactive } from 'vue'

const variable = 0

const refVariable = ref(0)

const reactiveVariable = reactive({data : 0})

let myTimer;
function startTimer(){
    myTimer = setInterval(() => {
        console.log('setInterval')
        refVariable.value +=1;
        reactiveVariable.data +=1;
    }, 1000);
}

function stopTimer(){
    clearInterval(myTimer);
}

</script>

<template>
    <main>
        <span>{{ variable }} - </span>
        <span>{{ refVariable }} - </span>
        <span>{{ reactiveVariable.data }} </span>
        <br>
        <button @click="startTimer">START</button>
        <br>
        <button @click="stopTimer">END</button>

    </main>
</template>
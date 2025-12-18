<script setup>
    import { ref } from 'vue';

    const indexActuel = ref(0);

    function change() {
        indexActuel.value--;

        if (indexActuel.value < 0){
            indexActuel.value = 2
        }
    }
    
</script>

<template>
    <div class="rectangle" v-if="indexActuel === 0">
        <div class="circle red">
            <span v-show="indexActuel === 0" class="text-stop">STOP</span>
        </div>
        <div class="circle"></div><div class="circle"></div>
    </div>
    <div class="rectangle" v-else-if="indexActuel === 1">
        <div class="circle"></div> <div class="circle orange"></div><div class="circle"></div>
    </div>
    <div class="rectangle" v-else-if="indexActuel === 2">
        <div class="circle"></div> <div class="circle"></div><div class="circle green"></div>
    </div>
    <div>
        <button @click="change()">change</button>
    </div>
</template>

<style scoped>
    .circle {
        background-color: #fff;
        border: 1px solid black;
        height: 100px;
        border-radius: 50%;
        width: 100px;
    }

    .red {
        background-color:red;
    }

    .orange {
        background-color:orange;
    }

    .green {
        background-color:green;
    }

    .rectangle {
        display: flex;           
        flex-direction: column;  
        width: 120px;            
        background-color: #333;  
        padding: 10px;           
        border-radius: 15px;     
        gap: 10px;               
        align-items: center;
    }
</style>
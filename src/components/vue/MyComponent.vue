<script setup>

import { ref } from 'vue';
const name = "Chanchito Feliz"
let counter = ref(5)

let characters = ref([])

function add(){
    counter.value++
    characters.value.push(counter.value)    
}

function less(){
    counter.value--
    console.log(counter);
    
}

console.log("Hola mundo",name)

</script>

<template>
    <div class="mx-auto bg-blue-300 max-w-96 rounded py-4 px-6">
        Hola {{ name }}

        <div 
        v-if="counter > 0"
        class=" cursor-pointer flex items-center justify-center rounded-full text-white bg-blue-400 size-8"
        >
            {{ counter }}
        </div>
        <div v v-else >
            solo soy un tipo chill de cojone
      </div>
        <div 
        @click="add"
        class="hover:bg-green-300  cursor-pointer flex items-center justify-center rounded-full text-white bg-blue-400 size-8"
        >
            +
        </div>
        <div 
        @click="less"
        class=" cursor-pointer flex items-center justify-center rounded-full text-white bg-red-300 size-8"
        >
            -
        </div>

    </div>
    <div
    v-for="(name,index) in characters"
    :key="index"
    class="bg-blue-300 mb-1"
    >
    {{ name }}

    </div>

</template>
<script setup>
import { defineProps } from 'vue';
const props = defineProps(['url'])
</script>

<template>
  <div class="flex justify-center items-center flex-col  py-10">
    
    <p class="bg-gray-200 text-slate-900 text-center textju font-extrabold text-3xl py-6 w-full shadow-lg"> 
        <slot name="nomeservico"></slot> 
    </p>
    
    <img :src="props.url" alt="" class=" w-4/5 h-auto my-8 rounded shadow-xl">
    
    <div class="h-1/2 w-full flex justify-center items-center px-4">
        <ul class="w-full bg-white rounded-xl grid text-lg grid-cols-1 shadow-2xl p-">
            <slot name="servicos"></slot>
        </ul> 
    </div>
  </div>
</template>

<style scoped>
</style>
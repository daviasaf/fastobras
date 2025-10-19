<script setup>
import { defineProps } from 'vue';
const props = defineProps(['url'])
</script>

<template>
  <div class="flex justify-center items-center flex-col  mt-20 ">
    
    <p class="bg-gray-200 text-slate-900 text-center font-extrabold text-3xl py-6 w-4/5 shadow-lg rounded-t-2xl break-words"> 
        <slot name="nomeservico"></slot> 
    </p>
    
    <img :src="props.url" alt="" class=" w-4/5 h-auto shadow-xl">
    
    <div class="h-1/2 w-full flex justify-center items-center ">
        <ul class="w-4/5 bg-white rounded-b-2xl grid text-lg grid-cols-1 shadow-2xl p-">
            <slot name="servicos"></slot>
        </ul> 
    </div>
  </div>
</template>

<style scoped>
</style>
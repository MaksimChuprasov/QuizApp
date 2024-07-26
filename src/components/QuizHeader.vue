<script setup>
    import { defineProps } from 'vue';
  
  const {questionStatus, barPercentage} = defineProps(['questionStatus', 'barPercentage'])
</script>

<template>
    <header>
        <h1 class="text-3xl font-semibold mt-5 mb-3">Question {{questionStatus}}</h1>
        <div class="w-[300px] h-12 border-solid border-[3px] border-gray-500 rounded-lg">
            <div class="bar h-full w-0 rounded-md" :style="{width: barPercentage}">
            </div>
        </div>
    </header>
</template>

<style scoped>
    .bar {
        background: rgb(1,11,66);
        background: linear-gradient(48deg, rgba(1,11,66,1) 0%, rgba(9,52,121,1) 17%, rgba(17,154,171,1) 100%);
    }
</style>
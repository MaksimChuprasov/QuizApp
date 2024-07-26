<script setup>
import Card from '../components/Card.vue';
import q from "../data/data.json";
import {ref, watch} from "vue";

const quizes = ref(q)
const search = ref('')
watch(search, () => {
  quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>

<template>
  <div>
    <header class="mb-3 mt-8 flex items-center">
      <h1 class="text-3xl font-semibold mr-4">Quizes</h1>
      <input class="bg-gray-100 text-black p-3 rounded-lg" v-model.trim="search" type="text" placeholder="Search...">
    </header>
    <div class="flex flex-wrap mt-10">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
    </div>
  </div>
</template>
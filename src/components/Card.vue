<script setup>
import { defineProps } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter()
const {quiz} = defineProps(['quiz'])

const navigateToQuiz = () => {
    router.push(`/quiz/${quiz.id}`)
}
</script>

<template>
    <div class="card w-[310px] overflow-hidden rounded-lg mb-8 mr-5 cursor-pointer bg-gray-300 text-black" @click='navigateToQuiz'>
        <img class="w-full h-[190px] m-0" :src="quiz.img" alt="">
        <div class="p-2">
            <h2 class="font-bold text-xl">{{quiz.name}}</h2>
            <p class="text-md">{{quiz.questions.length}} questions</p>
        </div>
    </div>
</template>

<style>
    .card {
    box-shadow: 1px 1px 10px rgba(0,0,0,0.1);
    }
</style>
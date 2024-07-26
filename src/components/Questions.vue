<script setup>
import { defineProps, defineEmits } from "vue";

const { question } = defineProps(["question"]);
const emit = defineEmits(["selectOption"]);

const emitSelectedOption = (isCorrect) => {
  emit("selectOption", isCorrect);
};
</script>

<template>
  <div>
    <div class="mt-5">
      <h1 class="mb-8 text-4xl">{{ question.text }}</h1>
    </div>
    <div>
      <div
        v-for="option in question.options"
        :key="option.id"
        class="flex mb-8 cursor-pointer rounded-md"
        @click="emitSelectedOption(option.isCorrect)"
      >
        <p
          class="flex w-12 h-12 text-3xl items-center justify-center bg-blue-800 rounded-l-md"
        >
          {{ option.label }}
        </p>
        <div class="rounded-r-md w-full text-3xl px-5 bg-blue-500 flex">
          <p class="pt-1">{{ option.text }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

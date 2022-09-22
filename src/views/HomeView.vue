<script setup>
// import TheWelcome from '../components/TheWelcome.vue'
import { useCounterStore } from '@/store/counter.js'
import { storeToRefs } from 'pinia';

const useCounter = useCounterStore()

const { increment } = useCounter
const { double, count } =storeToRefs(useCounter)
</script>

<template>
  <main>
    <!-- <TheWelcome /> -->
    <h1>Home counter :{{ count }}</h1>
    <h2>Double: {{ double }}</h2>
    <button @click="increment" class="btn btn-primary" >Increment</button>
  </main>
</template>

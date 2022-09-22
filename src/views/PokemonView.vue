<script setup>
import axios from "axios";
import { RouterLink } from "vue-router";
import { useGetData } from "@/composables/getData";

 
const { getData, data, loading, error } = useGetData();

getData("https://pokeapi.co/api/v2/pokemon");
</script>

<template>
  <h1>Pokemon</h1>

   

  <p v-if="loading">Cargando informacion...</p>
  <div class="alert alert-danger mt-2" v-if="error">{{ error }}</div>
  <div v-if="data" class="mb-3">
    <ul class="list-group mb-3">
      <li class="list-group-item" v-for="item in data.results" :key="item.name">
        <RouterLink :to="`/pokemon/${item.name}`">{{ item.name }}</RouterLink>
      </li>
    </ul>
    <button
      :disabled="!data.previous"
      class="btn btn-success me-2"
      @click="getData(data.previous)"
    >
      Previous
    </button>
    <button :disabled="!data.next" class="btn btn-primary" @click="getData(data.next)">
      Next
    </button>
  </div>
</template>

<script setup>
import { useFavoritosStore } from "@/store/favoritos";
import { storeToRefs } from "pinia";
import { RouterLink } from 'vue-router'

const useFavoritos = useFavoritosStore();
const { favoritos } = storeToRefs(useFavoritos);
const { remove } = useFavoritos;
</script>
<template>
  <h1>Favoritos :</h1>
  <p v-if="!favoritos.length">Sin favoritos</p>
  <template v-else>
    <div v-for="poke in favoritos" :key="poke.id" class="card mb-2">
      <div class="text-center">
        <img
          :src="poke.sprites?.other?.home?.front_default"
          alt=""
          class="rounded mx-auto d-block"
          width="400"
          height=""
        />
      </div>
      <div class="card-footer">
        <div class="d-flex align-items-center justify-content-center gap-1">
          <span class="badge text-bg-primary fw-bold fs-5">{{ poke.name }}</span>
           <router-link class="btn btn-warning btn-md fw-bold" :to="`/pokemon/${poke.name}`">
            Mas informacion
          </router-link>
          <button class="btn btn-success btn-md fw-bold" @click="remove(poke.id)">
            Eliminar
          </button>
        </div>
      </div>
    </div>
  </template>
</template>

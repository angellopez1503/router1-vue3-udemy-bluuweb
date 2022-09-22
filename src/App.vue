<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <nav class="navbar bg-dark navbar-dark">
    <div class="container">
      <router-link class="navbar-brand" to="/">
        <img
          src="@/assets/logo.svg"
          alt="Logo"
          width="30"
          height="24"
          class="d-inline-block align-text-top"
        />
        PokeAPI
      </router-link>
      <div>
        <router-link active-class="active" class="btn btn-outline-primary me-2" to="/">Home</router-link>
        <router-link active-class="active" class="btn btn-outline-primary me-2" to="/pokemon">Pokemons</router-link>
        <router-link active-class="active" class="btn btn-outline-primary" to="/favoritos">Favoritos</router-link>
      </div>
    </div>
  </nav>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/pokemon">Pokemon</RouterLink>
      </nav>
    </div>
  </header> -->
  <div class="container text-center">
    <RouterView />
  </div>
  
</template>

<style scoped>
 
</style>

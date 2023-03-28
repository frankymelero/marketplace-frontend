<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
   <header>
        <div class="container">
            <p class="logo">Easy Task</p>
            <nav>
              <RouterLink to="/about">Sobre Nosotros</RouterLink> 
              <RouterLink to="/shop">Tienda</RouterLink>  
              <RouterLink to="/login">Login</RouterLink> 
              <RouterLink to="/registrer">Registrarse</RouterLink> 
              <RouterLink to="/support">Soporte técnico</RouterLink>
            </nav>
        </div>
    </header>
  </template>

  
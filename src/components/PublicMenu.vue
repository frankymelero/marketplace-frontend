<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
   <header>
        <div class="container">
            <p class="logo"><RouterLink to="/">Easy Task</RouterLink></p>
            <nav>
              <RouterLink to="/about">Sobre Nosotros</RouterLink> 
              <RouterLink to="/shop">Tienda</RouterLink>  
              <RouterLink to="/login">Login</RouterLink> 
              <RouterLink to="/register">Registrarse</RouterLink> 
              <RouterLink to="/support">Soporte técnico</RouterLink>

              <!-- este hay que borrarlo -->
              <RouterLink to="/account">Perfil de usuario</RouterLink>
            </nav>
        </div>
    </header>
  </template>
  
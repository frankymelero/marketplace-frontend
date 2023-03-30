<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
   <header>
        <div class="container">
            <p class="logo">Easy Task</p>
            <nav>
              <RouterLink to="/home">Tu tienda</RouterLink>  
              <RouterLink to="/about-us">Sobre Nosotros</RouterLink> 
              <RouterLink to="/support">Soporte técnico</RouterLink>
              <RouterLink to="/account">Perfil de usuario</RouterLink>
              <RouterLink to="/">Cerrar Sesión</RouterLink>
            </nav>
        </div>
    </header>
  </template>

  
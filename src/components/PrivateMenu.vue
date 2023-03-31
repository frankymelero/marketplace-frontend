
<template>
   <header>
        <div class="container">
            <p class="logo">Easy Task</p>
            <nav>
              <RouterLink to="/home">Tu tienda</RouterLink>  
              <RouterLink to="/about-us">Sobre Nosotros</RouterLink> 
              <RouterLink to="/support">Soporte técnico</RouterLink>
              <RouterLink to="/account">Perfil de usuario</RouterLink>
              <a href="#" @click.prevent="logout">Cerrar sesión</a>
            </nav>
        </div>
    </header>
  </template>
<script>
import { RouterLink } from 'vue-router';
import router from '../router/index.js';

export default {
  components: { RouterLink, router},
  methods: {
    logout() {
  localStorage.setItem('username', '');
  localStorage.setItem('logged', false);
  window.location.href="http://localhost:5173/login";
    },
  },
};
</script>
  
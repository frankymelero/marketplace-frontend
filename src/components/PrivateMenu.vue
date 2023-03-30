
<template>
   <header>
        <div class="container">
            <p class="logo"><RouterLink to="/home">Easy Task</RouterLink></p>
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
  router.push('/login');
    },
  },
};
</script>
  
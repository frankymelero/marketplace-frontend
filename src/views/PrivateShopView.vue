<template>

    <PrivateMenu />
    <!-- Esto es una tienda con los productos que vendemos como cursos o web estaticas simples de maquetacion sencillas
    Las webs que venderiamos como producto serian web basicas y estaticas que pueden ser (me lo invento) 50€, para intentar venderles a los clientes una afiliacion periodica para mantenimiento y actualizacion de la web, vendemos la web barata para atraer y ganar clientes mensuales.
    los cursos que vendemos (es porque el cesar lo queria con cursos tambien, hay que preguntarle si tiene algun curso montado para subirlo al repo) -->
    <div class="about">
        <h2 class="hola">Necesitas una página web?</h2>
       <p>Tienda</p>

        <img src="../assets/img/taskeasylogo.jpg">


    <Footer></Footer>
</div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import PrivateMenu from '../components/PrivateMenu.vue';
import Footer from '../components/Footer.vue';
import router from '../router/index.js';

const isLogged = ref(localStorage.getItem('logged'));

onMounted(() => {
  if (isLogged.value !== "si") {
    router.push('/login');
  }
});

</script>
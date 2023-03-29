<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
<PublicMenu/>
  <div class="about">

    <div class="login-form">
      <h1>Register Page</h1>
    <form action="">
      <label for="name">Nombre</label><br/>
      <input type="text" id="username" placeholder="Introduce el nombre"><br/>
      <label for="username">Usuario</label><br/>
      <input type="text" id="username" placeholder="Introduce el usuario"><br/>

      <label for="username">E-mail</label><br/>
      <input type="text" id="username" placeholder="Introduce el usuario"><br/>
      <label for="password">Contraseña</label><br/>
      <input type="password" id="password" placeholder="Introduce la contraseña"><br/>
      <label for="password2">Repite la contraseña</label><br/>
      <input type="password" id="password2" placeholder="Introduce la contraseña"><br/><br/>
      <input type="submit"><br>
    
    </form>
  </div>
  </div>

  <Footer></Footer>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

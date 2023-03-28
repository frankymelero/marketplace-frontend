<script setup>
import PublicMenu from '../components/PublicMenu.vue';
</script>

<template>
<PublicMenu/>
  <div class="about">

    <div class="login-form">
      <h1>Register Page</h1>
    <form action="">
      <label for="username">Usuario</label><br/>
      <input type="text" id="username" placeholder="Introduce el usuario"><br/>
      <label for="password">Contraseña</label><br/>
      <input type="password" id="password" placeholder="Introduce la contraseña"><br/><br/>
      <input type="submit"><br>
      <p>¿No tienes cuenta? <RouterLink to="/register">Registrate</RouterLink></p>
    </form>
  </div>
  </div>

  
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

<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
<PublicMenu/>
  <div class="about">

    <div class="login-form">
      <h1>Login</h1>
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


  <Footer></Footer>
</template>

<style scoped>
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;

}

.login-form {
  background-color: #ffffff;
  padding: 40px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.507);
  max-width: 400px;
  width: 100%;
}

.login-form h1 {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 20px;
}

.login-form label {
  display: block;
  font-size: 1.2rem;
  margin-bottom: 5px;
}

.login-form input[type="text"],
.login-form input[type="password"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 1rem;
  border: 2px solid #cccccc;
  border-radius: 5px;
}

.login-form input[type="submit"] {
  background-color: #614caf;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.2rem;
}

.login-form input[type="submit"]:hover {
  background-color: #3e7b8e;
}

.login-form p {
  margin-top: 20px;
  font-size: 1.2rem;
  text-align: center;
}

.login-form p a {
  color: #664caf;
}

</style>
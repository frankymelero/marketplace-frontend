<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
<PublicMenu/>
  <div class="about">

    <div class="login-form">
      <h1>Register</h1>
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


<style scoped>
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.login-form,
.register-form {
  background-color: #ffffff;
  padding: 40px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.3);
  max-width: 400px;
  width: 100%;
}

.login-form h1,
.register-form h1 {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 20px;
}

.login-form label,
.register-form label {
  display: block;
  font-size: 1.2rem;
  margin-bottom: 5px;
}

.login-form input[type="text"],
.login-form input[type="password"],
.register-form input[type="text"],
.register-form input[type="password"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 1rem;
  border: 2px solid #cccccc;
  border-radius: 5px;
}

.login-form input[type="submit"],
.register-form input[type="submit"] {
  background-color: #614caf;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.2rem;
}

.login-form input[type="submit"]:hover,
.register-form input[type="submit"]:hover {
  background-color: #3e7b8e;
}

.login-form p,
.register-form p {
  margin-top: 20px;
  font-size: 1.2rem;
  text-align: center;
}

.login-form p a,
.register-form p a {
  color: #664caf;
}

/* Estilos para el botón de registro */

.btn-register {
  display: block;
  margin: auto;
  background-color: #4CAF50;
  color: #ffffff;
  font-size: 1.2rem;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  margin-top: 20px;
}

.btn-register:hover {
  background-color: #3e8e41;
}



</style>



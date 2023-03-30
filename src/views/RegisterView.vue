<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
<PublicMenu/>
  <div class="about">
    <div class="register-form">
      <h1>Registro</h1>
      <form action="">
        <label for="name">Nombre</label><br/>
        <input type="text" id="name" placeholder="Introduce el nombre"><br/>
        <label for="username">Usuario</label><br/>
        <input type="text" id="username" placeholder="Introduce el usuario"><br/>
        <label for="email">E-mail</label><br/>
        <input type="email" id="email" placeholder="Introduce el correo electrónico"><br/>
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
  min-height: calc(100vh - 50px);
  padding-bottom: 50px;
}

.register-form {
  background-color: #ffffff;
  padding-left: 5vh;
  padding-right: 5vh;
  padding-bottom: 5vh;
  padding-top: 2vh;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.3);
  max-width: 40vh;
  width: 80%;
  max-width: 80vh;
  margin-top: 10vh;
}

.register-form h1 {
  text-align: center;
  font-size: 2rem;
}

.register-form label {
  display: block;
  font-size: 1.2rem;
  margin-bottom: 5px;
}

.register-form input[type="text"],
.register-form input[type="password"],
.register-form input[type="email"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 1rem;
  border: 2px solid #cccccc;
  border-radius: 5px;
}

.register-form input[type="submit"] {
  background-color: #614caf;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.2rem;
}

.register-form input[type="submit"]:hover {
  background-color: #3e7b8e;
}



@media (max-width: 768px) {
  .register-form {
    max-width: 90%;
    padding: 3vh;
  }
}
</style>

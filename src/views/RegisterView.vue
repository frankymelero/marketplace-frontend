

<template>
  <PublicMenu />
  <div class="about">
    <div class="login-form">
      <h1>Register</h1>
      <form>
        <label for="name">Nombre</label><br />
        <input type="text" ref="nameInput" v-model="state.name" placeholder="Introduce el nombre" /><br />
        <label for="username">Usuario</label><br />
        <input type="text" ref="usernameInput" v-model="state.username" placeholder="Introduce el usuario" /><br />

        <label for="email">E-mail</label><br />
        <input type="text" ref="emailInput" v-model="state.email" placeholder="Introduce el email" /><br />
        <label for="password">Contraseña</label><br />
        <input type="password" ref="passwordInput" v-model="state.password" placeholder="Introduce la contraseña" /><br />
        <label for="password2">Repite la contraseña</label><br />
        <input type="password" ref="password2Input" v-model="state.password2" placeholder="Introduce la contraseña" /><br /><br />
        <button type="submit" @click.prevent="handleSubmit">Enviar</button><br />
        
      </form>
    </div>
  </div>
  <Footer />
</template>

<script>
import { reactive, ref } from 'vue';
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
import router from '../router/index.js';
export default {
  components: { PublicMenu, Footer },
  setup() {
    const state = reactive({
      name: '',
      username: '',
      email: '',
      password: '',
      password2: '',
    });

    const nameInput = ref(null);
    const usernameInput = ref(null);
    const emailInput = ref(null);
    const passwordInput = ref(null);
    const password2Input = ref(null);
//Pendiente comprobación en la API si existe algún usuario que se llame igual, en el caso que lo exista no debe dar de alta y debe mostrar un mensaje que indique que el usuario ya está registrado.
//Pendiente escapar, y forzar ciertos caracteres en cada campo, para que introduzcan la información en el formato que queremos, y no hayan cosas raras en la bbdd.

    function createUser(name, username, email, password1, password2){
  const url = 'http://127.0.0.1:8080/users/new';
  const data = {
    id: 0,
    name: name,
    username: username,
    password: password1,
    email: email
  };

  if(password1 === password2){
  fetch(url, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(data)
  })
  .then(response => response.json())
  .then(data => console.log(data))
  .then(alert("Registro completado!"))
  .then(router.push('/login'))
  .catch(error => console.error(error));
}else{
  alert("Las contraseñas no coinciden");
}
}

const handleSubmit = () => {
  createUser(state.name, state.username, state.email, state.password, state.password2);
};

    return {
      state,
      nameInput,
      usernameInput,
      emailInput,
      passwordInput,
      password2Input,
      handleSubmit,
    };
  },
};
</script>

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



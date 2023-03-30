

<template>
  <PublicMenu />
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

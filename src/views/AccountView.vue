<template>
  <PrivateMenu />
  <div class="account-view">
    <h1>Mi cuenta</h1>

    <div class="card account-details">
      <h3>Detalles de la cuenta</h3>
      <p>Bienvenido {{ user.name }}.</p>

      <form @submit.prevent="updateEmail">
        <div class="form-group">
          <label for="email">Correo electrónico:</label>
          <input type="email" ref="emailInput" id="email" v-model="user.email" required />
        </div>

        <div class="form-group">
          <button type="submit">Actualizar correo electrónico</button>
        </div>
      </form>
    </div>

    <div class="card password-change">
      <h3>Cambiar contraseña</h3>
      <form @submit.prevent="changePassword">
        <div class="form-group">
          <label for="current-password">Contraseña actual:</label>
          <input type="password" id="current-password" v-model="passwords.current" required />
        </div>

        <div class="form-group">
          <label for="new-password">Nueva contraseña:</label>
          <input type="password" id="new-password" v-model="passwords.new" required />
        </div>

        <div class="form-group">
          <label for="confirm-password">Confirmar nueva contraseña:</label>
          <input type="password" id="confirm-password" v-model="passwords.confirm" required />
        </div>

        <div class="form-group">
          <button type="submit">Cambiar contraseña</button>
        </div>
      </form>
    </div>

  </div>
  <Footer></Footer>
</template>
 
<script setup>
import { ref, onMounted } from 'vue';
import PrivateMenu from '../components/PrivateMenu.vue';
import Footer from '../components/Footer.vue';
import router from '../router/index.js';
//Funciones fetch.



// Datos
const iduser = localStorage.getItem('id');
const username = localStorage.getItem('username');
const isLogged = ref(localStorage.getItem('logged'));
let contra = localStorage.getItem('pass');
const user = ref({
  email: '',
});
const passwords = ref({
  current: '',
  new: '',
  confirm: '',
});

// Métodos

async function updateUserEmail(email, username) {
  const url = `http://127.0.0.1:8080/users/update/${username}`;

  const data = {
    id: iduser,
    name: user.value.name,
    username: user.value.username,
    password: user.value.password,
    email: email
  };

  try {
    const response = await fetch(url, {
      method: 'PUT',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(data)
    });
    const result = await response.json();
    if(result){
      alert("Email modificado!");
    }
  } catch (error) {
    console.error(error);
  }
}


async function updateUserPassword(oldpassword, oldpasswordinput, password1, password2) {

  if(password1 !== password2){
alert("Las contraseñas no coinciden");
  }else if(oldpassword !== oldpasswordinput){

  }else if(oldpassword === oldpasswordinput && password1 === password2){
    const url = `http://127.0.0.1:8080/users/update/${username}`;

const data = {
  id: iduser,
  name: user.value.name,
  username: user.value.username,
  password: password1,
  email: user.value.email
};

try {
  const response = await fetch(url, {
    method: 'PUT',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(data)
  });
  const result = await response.json();
  if(result){
    alert("Contraseña Modificada!");

  }
} catch (error) {
  console.error(error);
}
  }else{
    alert("Los datos no coinciden");
  }
  
}
function updateEmail() {
 updateUserEmail(user.value.email, username);
}

function changePassword() {
  updateUserPassword(contra, passwords.value.current, passwords.value.new, passwords.value.confirm)
}

 

onMounted(() => {
  if (isLogged.value !== "si") {
    router.push('/login');
  }
 
  async function getUserData() {
    try {
      const response1 = await fetch(`http://127.0.0.1:8080/users/get-user/${iduser}`);
      const data1 = await response1.json();
      user.value = data1;
      return data1;

    } catch (error) {
      console.error(error);
    }
  }
  getUserData();


});






</script>
<style scoped>

.account-view {
  max-width: 800px;
  margin: 0 auto;
  padding: 30px 0;
  text-align: center;
}

.account-view h1 {
  font-size: 36px;
  margin-bottom: 20px;
}

.card {
  margin-top: 30px;
  display: inline-block;
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  padding: 30px;
  margin-bottom: 20px;
  text-align: left;
  width: 100%;
  box-sizing: border-box;
}

.card h3 {
  font-size: 24px;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  font-size: 18px;
  margin-bottom: 5px;
}

.form-group input[type="email"],
.form-group input[type="password"] {
  width: 100%;
  padding: 10px;
  border: none;
  border-bottom: 2px solid #ccc;
  font-size: 16px;
  margin-bottom: 10px;
  box-sizing: border-box;
}

.form-group input[type="email"]:focus,
.form-group input[type="password"]:focus {
  outline: none;
  border-bottom: 2px solid #0077ff;
}

.form-group button[type="submit"] {
  background-color: #0077ff;
  border: none;
  color: #fff;
  padding: 10px 20px;
  font-size: 18px;
  border-radius: 5px;
  cursor: pointer;
}

.form-group button[type="submit"]:hover {
  background-color: #005ae6;
}

h1{
  margin-top: 120px;
}

.account-details {
  max-width: 600px;
}
.password-change {
  max-width: 700px;
}


</style>
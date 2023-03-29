<template>
    <PublicMenu/>
    <div class="account-view">
      <h1>Mi cuenta</h1>
      <div class="account-details">
        <h3>Detalles de la cuenta</h3>
        <form @submit.prevent="updateEmail">
          <label for="email">Correo electrónico:</label>
          <input type="email" id="email" v-model="user.email" required />
  
          <button type="submit">Actualizar correo electrónico</button>
        </form>
      </div>
      <div class="password-change">
        <h3>Cambiar contraseña</h3>
        <form @submit.prevent="changePassword">
          <label for="current-password">Contraseña actual:</label>
          <input type="password" id="current-password" v-model="passwords.current" required />
  
          <label for="new-password">Nueva contraseña:</label>
          <input type="password" id="new-password" v-model="passwords.new" required />
  
          <label for="confirm-password">Confirmar nueva contraseña:</label>
          <input type="password" id="confirm-password" v-model="passwords.confirm" required />
  
          <button type="submit">Cambiar contraseña</button>
        </form>
      </div>
      
    </div>
    <Footer></Footer>
  </template>
  
  <script setup>
import { ref, onMounted } from 'vue';
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';

// Datos
const user = ref({
  email: '',
});
const passwords = ref({
  current: '',
  new: '',
  confirm: '',
});

// Métodos
function updateEmail() {
  console.log('Actualizar correo electrónico');
  // Aquí puedes llamar a tu API para actualizar el correo electrónico del usuario.
}

function changePassword() {
  console.log('Cambiar contraseña');
  // Aquí puedes llamar a tu API para cambiar la contraseña del usuario.
}

// Ciclo de vida
onMounted(() => {
  // Simulación de datos del usuario, reemplazar con la llamada a la API para obtener la información del usuario
  user.value = {
    email: 'juan.perez@example.com',
  };
});
</script>
  
  <style scoped>
  .account-view {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .account-details,
  .password-change {
    width: 100%;
    max-width: 500px;
    margin-bottom: 2rem;
  }
  
  form {
    display: flex;
    flex-direction: column;
  }
  
  label {
    margin: 1rem 0 0.5rem;
  }
  
  input {
    width: 100%;
    padding: 0.5rem;
    font-size: 1rem;
  }
  
  button {
    margin-top: 1rem;
    padding: 0.5rem;
    font-size: 1rem;
    cursor: pointer;
  }
  </style>
  


<template>
  <PrivateMenu/>
    <div class="support">
      <h1>Soporte Técnico</h1>
      <p>
        ¿Necesitas ayuda con nuestros servicios o cursos? Estamos aquí para ayudarte.
      </p>
      
      <div class="support-form">
        <h2>Formulario de contacto</h2>
        <form @submit.prevent="submitForm">
          <div class="form-group">
            <label for="name">Nombre:</label>
            <input type="text" id="name" v-model="form.name" required />
          </div>
  
          <div class="form-group">
            <label for="email">Correo electrónico:</label>
            <input type="email" id="email" v-model="form.email" required />
          </div>
  
          <div class="form-group">
            <label for="message">Mensaje:</label>
            <textarea id="message" v-model="form.message" required></textarea>
          </div>
  
          <button type="submit">Enviar</button>
        </form>
      </div>
    </div>
    <Footer></Footer>
  </template>
  
  <script setup>
  import PrivateMenu from '../components/PrivateMenu.vue';
  import Footer from '../components/Footer.vue';
  import { ref } from 'vue';
  
  // Datos
  const form = ref({
    name: '',
    email: '',
    message: '',
  });
  
  // Métodos
  function submitForm() {
    // Aquí puedes añadir la lógica para procesar el formulario, como enviarlo a una API o a un correo electrónico.
    console.log('Formulario enviado:', form.value);
    alert('Tu mensaje ha sido enviado. Nos pondremos en contacto contigo lo más pronto posible.');
  }
  </script>
  
  <style scoped>
  .support {
    max-width: 600px;
    margin: 0 auto;
  }
  
  .form-group {
    margin-bottom: 1rem;
  }
  
  label {
    display: block;
    margin-bottom: 0.5rem;
  }
  
  input,
  textarea {
    width: 100%;
    padding: 0.5rem;
    font-size: 1rem;
    border: 1px solid #ccc;
  }
  
  button {
    background-color: #007bff;
    color: #fff;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    border: none;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  
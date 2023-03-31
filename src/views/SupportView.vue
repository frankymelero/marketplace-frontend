
<template>
  <PrivateMenu/>
    <div class="support">
      <h1>Soporte Técnico</h1>
      <p>
        ¿Necesitas ayuda con nuestros servicios o cursos? Estamos aquí para ayudarte.
      </p>
      
      <div class="support-form">
        <h2>Formulario de contacto</h2>
        <form ref="formu" @submit.prevent="submitForm">
          <div class="form-group">
            <label for="name">Nombre:</label>
            <input type="text" id="name" name="name" v-model="form.name" required />
          </div>
  
          <div class="form-group">
            <label for="email">Correo electrónico:</label>
            <input type="email"  name="email" id="email" v-model="form.email"  required />
          </div>
  
          <div class="form-group">
            <label for="message">Mensaje:</label>
            <textarea id="message" name="message" v-model="form.message"  required></textarea>
          </div>
  
          <button type="submit" class="submit-button" >Enviar</button>
        </form>
      </div>
    </div>
    <Footer></Footer>
</template>
  <script setup>
    
  import emailjs from 'emailjs-com';
  import { ref, onMounted } from 'vue';
  import PrivateMenu from '../components/PrivateMenu.vue';
  import Footer from '../components/Footer.vue';
  import router from '../router/index.js';
  
  const isLogged = ref(localStorage.getItem('logged'));
  
  const formu = ref(null);
const inputFieldReset = ref(null);

const sendMail = () => {
  emailjs
    .sendForm('service_ugh2jxp', 'template_5d30ygk', formu.value, 'UJc6rUhAnbit4DOGE')
    .then(
      () => {
        alert('Message sent!');
        inputFieldReset.value = ' ';
      },
      (error) => {
        alert('Message not sent', error);
      }
    );
};

  onMounted(() => {
    if (isLogged.value !== "si") {
      router.push('/login');
    }

  });
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
    sendMail();
  }


  </script>
  
  <style scoped>
  .support {
    padding: 30px 0;
    text-align: center;
  }
  .support h1 {
    font-size: 36px;
    margin-bottom: 20px;
  }
  .support p {
    font-size: 18px;
    margin-bottom: 30px;
  }
  .support-form {
    display: inline-block;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    padding: 30px;
    margin: 0 auto;
    text-align: left;
    width: 500px;
    height: 400px;
  }
  .support-form h2 {
    font-size: 24px;
    margin-bottom: 20px;
  }
  .support-form .form-group {
    margin-bottom: 20px;
  }
  .support-form label {
    display: block;
    font-size: 18px;
    margin-bottom: 5px;
  }
  .support-form input[type="text"],
  .support-form input[type="email"],
  .support-form textarea {
    width: 100%;
    padding: 10px;
    border: none;
    border-bottom: 2px solid #ccc;
    font-size: 16px;
    margin-bottom: 10px;
    box-sizing: border-box;
  }
  .support-form input[type="text"]:focus,
  .support-form input[type="email"]:focus,
  .support-form textarea:focus {
    outline: none;
    border-bottom: 2px solid #0077ff;
  }
  .support-form button[type="submit"] {
    background-color: #0077ff;
    border: none;
    color: #fff;
    padding: 10px 20px;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
    margin-left: -30px;
  }
  .support-form button[type="submit"]:hover {
    background-color: #005ae6;
  }
  h1{
    margin-top: 120px;
  }
  footer{
    margin-top: 20.9vh;
  }
  .support-form .submit-button {
  width: 113.5%;
  max-width: 6000px;
  margin-top: -4px;
}
</style>
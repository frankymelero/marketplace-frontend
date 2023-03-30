<template>
    <PrivateMenu />
    <div class="product-view">
      <p>Por hacer.</p>
      <div class="product-card">
       <div class="left-flex">
          <img class="product-logo" :src="products.urlimg" :alt="products.name" />
        </div>
        <div class="product-info">
          <h3 class="product-name">{{ products.name }}</h3>
          <p class="product-description">{{ products.description }}</p>
          <p class="product-price">Precio: {{ products.price }}</p>
          <p class="product-delivery">{{ products.entrega }}</p>  
          
          <input type="button" id="mostrarformulario" value="Solicitar servicio" @click="mostrarFormulario"/>

          <form id="formulariomensaje">
          <div id="formulario">
         
                <label for="nombre">Nombre: </label>
                <input type="text" id="nombre" :value="user.name" required />
                <label for="email">E-mail: </label>
                <input type="text" id="email" :value="user.email" required /><br>
                <textarea name="message" id="mensaje" cols="60" rows="15"></textarea>
        
            
          </div>
          
          <input type="button" id="sendbutton" value="Enviar solicitud">
        </form>
        </div>
      </div>   
    </div>
    <Footer />
  </template>
  
  <script setup>
  import PrivateMenu from '../components/PrivateMenu.vue';
  import Footer from '../components/Footer.vue';
  import { useRoute } from 'vue-router';
  import { ref, onMounted } from 'vue';
  
  const iduser = localStorage.getItem("id");
  const products = ref([]);
  const user = ref([]);

  const route = useRoute();
  
  function mostrarFormulario() {
  const formulario = document.getElementById('formulariomensaje');
  const botonMostrar = document.getElementById('mostrarformulario');
  formulario.style.display = 'block';
  botonMostrar.style.display = 'none';
}

  onMounted(() => {
const id = route.params.id;

console.log(id);
 
    fetch(`http://127.0.0.1:8080/services/get/${id}`)
      .then(response => response.json())
      .then(data => {
        data.urlimg = `../${data.urlimg}`;
        products.value = data;
      })
      .catch(error => {
        console.log(error);
      });

      fetch(`http://127.0.0.1:8080/users/get-user/${iduser}`)
      .then(response => response.json())
      .then(data => {
        data.urlimg = `../${data.urlimg}`;
        user.value = data;
        console.log(data);
      })
      .catch(error => {
        console.log(error);
      });

  });
  </script>
  
<style scoped>

.product-view{
    min-height: 100vh;
    padding-top: 20vh;
    text-align: left;
   
}
.product-card{
    display:flex;
    background-color: white;
    max-height: 61vh;
    padding-right: 5vw;
}
.left-flex{
    min-height: 61vh;
    min-width: 50vw;
    display:flex;
    justify-content: center;
}
.product-logo{
    height: 40vh;
    margin-top: 10vh;
    border: 3px solid rgba(0,0,0,0.3)
 
}

label[for]{
    font-size: 25px;
}
label[for=email]{
    margin-left: 3vw;
  }
  #sendbutton{
    margin-left: 4vw;
    width: 250px;
    height: 50px;
    border: 2px solid black;
    border-radius: 40px;
    background-color: #007bff;
    color: white;
    font-size: 29px;
    transition: 0.4s;
    margin: 2vh 0vw;
    
 
  }
  #mensaje{
    margin-top: 1vh;
  }
  #sendbutton:hover{
 
    transition: 0.4s;
    box-shadow: 0px 2px 5px black;
    cursor: pointer;
  }

  form#formulariomensaje{
    display: none;
  }
  #mostrarformulario{
    margin-top: 5vh;
    width: 250px;
    height: 50px;
    border: 2px solid black;
    border-radius: 40px;
    background-color: #007bff;
    color: white;
    font-size: 29px;
    transition: 0.4s;
    cursor:pointer;
  }
</style>
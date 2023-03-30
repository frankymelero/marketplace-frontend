<template>
  <PrivateMenu />
  <div class="products-container">
    <h2 class="products-title">Nuestros servicios</h2>

    <div v-for="product in products" :key="product.id" class="product-card">
      <RouterLink :to="{ path: '/product-view/' + product.id }"><img class="product-logo" :src="product.urlimg" :alt="product.name" /></RouterLink> 
            <div class="product-info">
                <h3 class="product-name">{{ product.name }}</h3>
                <p class="product-description">{{ product.description }}</p>
                <p class="product-price">Precio: {{ product.price }}</p>
                <p class="product-delivery">{{ product.entrega }}</p>
              
            </div>
        </div>   
    </div>
  <Footer></Footer>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import PrivateMenu from '../components/PrivateMenu.vue';
import Footer from '../components/Footer.vue';
import router from '../router/index.js';

const isLogged = ref(localStorage.getItem('logged'));
const products = ref([]);

onMounted(() => {
  if (isLogged.value !== 'si') {
    router.push('/login');
  } else {
    fetch('http://127.0.0.1:8080/services/get-all')
      .then(response => response.json())
      .then(data => {
        products.value = data;
      })
      .catch(error => {
        console.log(error);
      });
  }
});
</script>


  
<style scoped>
.products-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #ffffff;
    font-family: 'Roboto', sans-serif;
    min-height: 94.65vh;
}
.product-logo:hover {
    filter: brightness(70%);
  cursor:pointer;
}

.products-title {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: #333333;
    font-weight: 300;
}

.product-card {
    
    display: flex;
    flex-direction: row;
    justify-content: center;
    max-width: 52%;
    margin: 0 auto;
    gap: 2rem; 
    padding: 1rem;
}

.product-logo {
   width: 210px !important;
   height: 210px !important;
    height: auto;
    margin-bottom: 1rem;
    border-radius: 10px;
    animation: led 8s linear infinite;
}

.product-info {
    text-align: left;
    flex: 1;
}

.product-name {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
}

.product-description {
    font-size: 1rem;
    margin-bottom: 0.5rem;
}

.product-price {
    font-size: 1rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
}

.product-delivery {
    font-size: 1rem;
    margin-bottom: 0.5rem;
}

@media (max-width: 768px) {
    .product-card {
        flex-direction: column;
    }

    .product-info {
        max-width: 100%;
    }
}
@keyframes led {
  0%, 100% {
    box-shadow: 0 0 5px #0011ff, 0 0 10px #4c00ff, 0 0 15px #1900ff, 0 0 20px #2600ff;
  }
  25% {
    box-shadow: 0 0 5px #00aeff, 0 0 10px #00ccff, 0 0 15px #00c3ff, 0 0 20px #0099ff;
  }
  50% {
    box-shadow: 0 0 5px #9900ff, 0 0 10px #ff00d4, 0 0 15px #8c00ff, 0 0 20px #8c00ff;
  }
  75% {
    box-shadow: 0 0 5px #ffff00, 0 0 10px #ffff00, 0 0 15px #ffff00, 0 0 20px #ffff00;
  }
}
</style>

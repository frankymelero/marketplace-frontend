<template>
    <PrivateMenu />
    <div class="products-container">
        <h2 class="products-title">Nuestros servicios</h2>
        <div class="product-card">
            <img class="product-logo" src="../assets/img/taskeasylogo.jpg" alt="Logo del producto">
            <div class="product-info">
                <h3 class="product-name">Diseño Web Básico y Estático</h3>
                <p class="product-description">Impulsa tu negocio con nuestra oferta exclusiva en diseño web básico y
                    estático en WordPress o plataforma similar.</p>
                <p class="product-price">Precio: 120€ (20% de descuento ya aplicado)</p>
                <p class="product-delivery">Entrega exprés: Entre 7 y 15 días hábiles</p>
            </div>
        </div>
    </div>
    <Footer></Footer>
</template>
  
<script setup>
import PrivateMenu from '../components/PrivateMenu.vue';
import Footer from '../components/Footer.vue';
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
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 70%;
    margin: 0 auto;
    gap: 2rem; 
    padding: 1rem;
}

.product-logo {
    max-width: 20vh;
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
  
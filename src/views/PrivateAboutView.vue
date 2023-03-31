
<template>
    <PrivateMenu />
    <div class="about">
        <h1>Acerca de nosotros</h1>
    </div>
    <main class="container">
        <div class="about-us">
            <div class="about-us__content">
                <p>
                    Somos un equipo apasionado de tres estudiantes de programación front-end y back-end, unidos por nuestra
                    misión de crear sitios web atractivos y funcionales. Este proyecto es nuestro trabajo de final de
                    prácticas y estamos emocionados por embarcarnos en esta aventura juntos.
                </p>
                <p>
                    Nuestra meta es ofrecer nuestros servicios a clientes que buscan soluciones de diseño web asequibles sin
                    sacrificar calidad. Con nuestra combinación de habilidades y experiencia en programación, nos esforzamos
                    por brindar resultados excepcionales en cada proyecto que realizamos.
                </p>
            </div>
            <img class="about-us__image" src="../assets/img/nosotros.jpeg" alt="imagen nosotros" />
        </div>


        <section class="cards">
            <h2>¿Por qué elegirnos?</h2>
            <div class="card-grid">
                <div class="card">
                    <img class="card__image" src="../assets/img/precio.png" alt="mejor precio" />
                    <h3 class="card__title">El mejor precio</h3>
                    <p>Ofrecemos precios competitivos sin sacrificar la calidad de nuestro trabajo.</p>
                </div>
                <div class="card">
                    <img class="card__image" src="../assets/img/clientes.png" alt="para clientes" />
                    <h3 class="card__title">Enfoque en el cliente</h3>
                    <p>Nos esforzamos por satisfacer las necesidades de nuestros clientes y superar sus expectativas.</p>
                </div>
                <div class="card">
                    <img class="card__image" src="../assets/img/comprimos.png" alt="sin compromiso" />
                    <h3 class="card__title">Flexibilidad</h3>
                    <p>Trabajamos con flexibilidad para adaptarnos a las necesidades de nuestros clientes.</p>
                </div>
                <div class="card">
                    <img class="card__image" src="../assets/img/diseño.png" alt="diseño personalizado" />
                    <h3 class="card__title">Diseño personalizado</h3>
                    <p>Creamos diseños únicos y personalizados para cada cliente.</p>
                </div>
            </div>
        </section>
    </main>
    <Footer></Footer>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import PrivateMenu from '../components/PrivateMenu.vue';
import Footer from '../components/Footer.vue';
import router from '../router/index.js';

const isLogged = ref(localStorage.getItem('logged'));

onMounted(() => {
  if (isLogged.value !== "si") {
    router.push('/login');
  }
});



</script>

<style scoped>
.about {
    background-color: #f8f9fa;
    text-align: center;
    padding: 50px 0;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
}

.about-us {
    display:

        flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    padding: 50px 0;
}

.about-us__content {
    flex: 1;
    padding-right: 30px;
}

.about-us__image {
    max-width: 100%;
    flex: 1;
   box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.6);
}

.cards {
    padding: 50px 0;
}

.card-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 20px;
}

.card {
    flex: 0 0 48%;
    border: 1px solid #e0e0e0;
    border-radius: 4px;
    padding: 20px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    background-color: #fff;
    text-align: center;
}

.card__image {
    max-width: 80px;
    margin: 0 auto 15px;
}

.card__title {
    font-size: 20px;
    margin: 0 0 10px;
}

@media (min-width: 768px) {
    .about-us {
        flex-direction: row;
    }

    .about-us__content {
        padding-right: 50px;
    }

    .card {
        flex: 0 0 23%;
    }
}

@media (max-width: 767px) {
    .about-us {
        flex-direction: column;
    }

    .about-us__content {
        padding-right: 0;
    }

    .card {
        flex: 0 0 100%;
    }
}</style>
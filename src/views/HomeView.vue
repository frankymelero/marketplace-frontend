<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
import { RouterLink } from 'vue-router';
</script>

<template>
  <main>
 <PublicMenu/>
    <section id="hero">
        <h1>Easy Task</h1>
        <form action="">
<button><RouterLink to="/login">APLICA YA!</RouterLink></button>          
        </form>
    </section>

    <section id="descripcion">

        <div class="container">

            <div class="img-container"></div>
            <div class="texto">

                <h2> Hacemos la web de tus sueños </h2>
                <p>Llevamos tus sueños a la realidad digital con nuestro servicio de creación de sitios web personalizados. Nuestro equipo de profesionales se dedica a capturar tu visión y plasmarla en un sitio web atractivo, funcional y fácil de usar. Con un enfoque centrado en el usuario y una atención meticulosa a los detalles, nos aseguramos de que tu sitio web brille en línea y cause una impresión duradera en tus visitantes. Confía en nosotros para materializar la web de tus sueños y llevar tu negocio al siguiente nivel.</p>
            </div>
        </div>
    </section>

    <section id="nuestros-programas">
        <div class="container">
            <h2>Servicios</h2>
            <div class="programas">
                <div class="carta">
                    <h3>Diseño Web</h3>
                    <form action="">
                        <p>Transforma tu visión en una experiencia en línea única con nuestros servicios de diseño web personalizados. Nos enfocamos en crear sitios visualmente atractivos y funcionales, optimizados para dispositivos móviles y con una navegación intuitiva, para garantizar una experiencia de usuario excepcional. Impulsa tu negocio y destaca en el mundo digital con nuestro enfoque centrado en el usuario y la calidad de diseño.</p>
                        <button>+INFO</button>
                    </form>
                </div>
                <div class="carta">
                    <form action="">
                        <h3>Aplicaciones Web</h3>
                        <p>Maximiza la eficiencia de tu negocio y mejora la interacción con tus clientes mediante nuestras soluciones de aplicaciones web personalizadas. Desarrollamos aplicaciones web adaptadas a tus necesidades, utilizando las últimas tecnologías y siguiendo las mejores prácticas para garantizar un rendimiento superior, seguridad y escalabilidad. Lleva tu negocio al siguiente nivel con nuestras aplicaciones web a medida.</p>
                        <button>+INFO</button>
                    </form>
                </div>
                <div class="carta">
                    <h3>E-commerce</h3>
                    <form action="">
                        <p>Aprovecha el poder del comercio electrónico y expande tus oportunidades de negocio con nuestra solución de tienda en línea. Ofrecemos diseño y desarrollo de sitios web de comercio electrónico atractivos, fáciles de usar y seguros. Integramos diversas pasarelas de pago, gestión de inventario y seguimiento de pedidos, para que puedas vender tus productos y servicios de manera efectiva y sin complicaciones. Únete al mundo del comercio electrónico y aumenta tus ventas con nuestra ayuda.</p>
                        <button>+INFO</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <section id="caracteristicas">
        <div class="container">

            <ul>
                <li>✅Desarrolladores Preparados</li>
                <li>✅Consulta Gratuita sin compromiso</li>
                <li>✅Trabajo 24/7</li>
                <li>✅Presupuesto al alcance de todos</li>
            </ul>
        </div>
    </section>
  <Footer></Footer>
  </main>
</template>

<style scoped>

</style>

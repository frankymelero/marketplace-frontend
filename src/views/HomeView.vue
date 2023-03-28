<script setup>
import PublicMenu from '../components/PublicMenu.vue';
</script>

<template>
  <main>
 <PublicMenu/>
    <section id="hero">
        <h1>Easy Task</h1>
        <form action="">

            <button>APLICA YA!</button>
        </form>
    </section>

    <section id="descripcion">

        <div class="container">

            <div class="img-container"></div>
            <div class="texto">

                <h2> Hacemos la web de tus sueños </h2>
                <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Exercitationem dolores possimus impedit eos
                    porro optio accusamus debitis, voluptates in minus ut minima nesciunt fugit ipsam maiores qui.
                    Earum, magnam eaque!</p>
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
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae quisquam doloremque laborum
                            excepturi iure.</p>
                        <button>+INFO</button>
                    </form>
                </div>
                <div class="carta">
                    <form action="">
                        <h3>Aplicaciones Web</h3>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis ex minus deleniti
                            necessitatibus ipsum eum dolorum placeat.</p>
                        <button>+INFO</button>
                    </form>
                </div>
                <div class="carta">
                    <h3>E-commerce</h3>
                    <form action="">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat sed labore vitae ratione
                            assumenda alias voluptate dicta iusto?</p>
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
    <footer>
        <div class="container">
            <p>&copy; Easy Task Company</p>
        </div>
    </footer>
  </main>
</template>

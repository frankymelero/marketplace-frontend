<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
   <PublicMenu/>
  <div class="about">
    <h1>Nosotros</h1>
  </div>
  <main class="contenedor">
        <div class="nosotros">
            <div class="nosotros__contenido">
                <p>Somos un equipo apasionado de tres estudiantes de programación front-end y back-end, unidos por nuestra misión de crear sitios web atractivos y funcionales. Este proyecto es nuestro trabajo de final de prácticas, y estamos emocionados por embarcarnos en esta aventura juntos.
Nuestra meta es ofrecer nuestros servicios a clientes que buscan soluciones de diseño web asequibles sin sacrificar calidad. Con nuestra combinación de habilidades y experiencia en programación, nos esforzamos por brindar resultados excepcionales en cada proyecto que realizamos.

</p>

                <p>Al ser estudiantes ansiosos por adquirir experiencia y establecer relaciones duraderas con nuestros clientes, ofrecemos precios mucho más competitivos que los demás en el mercado. Creemos que el acceso a un diseño web profesional no debería ser un lujo, sino una posibilidad para todos.
Estamos comprometidos con la satisfacción de nuestros clientes y trabajamos incansablemente para superar sus expectativas. ¡Permítanos ser parte de su éxito en línea y ayudar a llevar su negocio al siguiente nivel! </p>
            </div>
            <img class="nosotros__imagen" src="../assets/img/nosotros.jpeg" alt="imagen nosotros">
        </div>
    </main>

    <section class="contenedro comprar">
        <h2 class="comprar__titulo">¿Por qué comprar con nosotros?</h2>

        <div class="bloques">

            <div class="bloque">
                <img class="bloque__imagen" src="../assets/img/precio.png" alt="porque comprar">
                <h3 class="bloque__titulo">El mejor precio</h3>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime, voluptatem et beatae ipsum officiis
                    nam aliquid </p>
            </div> <!--.bloque-->

            <div class="bloque">
                <img class="bloque__imagen" src="../assets/img/clientes.png" alt="porque comprar">
                <h3 class="bloque__titulo">Para Clientes</h3>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime, voluptatem et beatae ipsum officiis
                    nam aliquid </p>
            </div> <!--.bloque-->

            <div class="bloque">
                <img class="bloque__imagen" src="../assets/img/comprimos.png" alt="porque comprar">
                <h3 class="bloque__titulo">Sin compromiso</h3>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime, voluptatem et beatae ipsum officiis
                    nam aliquid </p>
            </div> <!--.bloque-->

            <div class="bloque">
                <img class="bloque__imagen" src="../assets/img/diseño.png" alt="porque comprar">
                <h3 class="bloque__titulo">Diseño personalizado</h3>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime, voluptatem et beatae ipsum officiis
                    nam aliquid </p>
            </div> <!--.bloque-->
        </div> <!--.bloques-->
    </section>
  <Footer></Footer>
</template>

<style scoped>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

p{
    margin-left: 15px;
}
h1{
    margin-top: -450px;
    margin-left: 18%;
}
.nosotros {
    display: grid;
    grid-template-rows: repeat(2, auto);
    margin-top: -570px;
}

@media (min-width: 768px) {
    .nosotros {
        grid-template-columns: repeat(2, 1fr);
        column-gap: 2rem;
    }
}

.nosotros__imagen {
    grid-row: 1 / 2;
}

@media (min-width: 768px) {
    .nosotros__imagen{
        grid-column: 2 / 3;
        width: 900px;
        border-radius: 10%;
    }
}

/** Bloques **/

.bloques {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
}

@media (min-width: 768px) {
    .bloques{
        grid-template-columns: repeat(4, 1fr);
    }
}
    


.bloque {
    text-align: center;
}

.bloque__titulo {
    margin: 0;

}

.bloque__imagen {
    width: 40%;
}
    
.nosotros__contenido{
    margin-top: 100px;
}

.comprar__titulo{
    margin-left: 35%;
}

</style>
<template>
    <PublicMenu />
    <div class="completo">
        <h2 class="promo-title">¿Necesitas una página web?</h2>

            <div class="descripcion">
                <img class="logo" src="../assets/img/taskeasylogo.jpg">
                <div class="text">
                <p>¡Impulsa tu negocio con nuestra oferta exclusiva en diseño web básico y estático!</p>
                <p>✅ Diseño web profesional en WordPress o plataforma similar<br> ✅ Precio increíble: ¡Sólo 120€! (20% de
                    descuento ya aplicado) <br>✅ Entrega exprés: Entre 7 y 15 días hábiles <br>✅ Cuestionario detallado para
                    personalizar tu
                    proyecto a la perfección</p>

                <p>Asegura tu presencia online con un sitio web atractivo, intuitivo y fácil de navegar. Esta oferta es
                    perfecta para emprendedores, pequeñas empresas y proyectos personales que buscan destacar en el mundo
                    digital.
                </p>
                <p>No esperes más, da el siguiente paso en tu aventura digital. Rellena nuestro cuestionario y comenzaremos
                    a
                    trabajar en tu proyecto de inmediato. ¡Aprovecha esta oportunidad única!</p>
                </div>
            </div>
        <Footer></Footer>
    </div>
</template>

<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<style scoped>
.completo { 
    text-align: center;
    align-items: center;

    background-color: #ffffff;

    font-family: 'Roboto', sans-serif;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.promo-title {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: #333333;
    font-weight: 300;
    margin-top: 10vh;
}

.logo {
    max-width: 50%;
    height: auto;
    margin-bottom: 1rem;
    border-radius: 10px;
}

.descripcion {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 70%;
    margin: 0 auto;
    gap: 2rem;

    min-height: 70vh; 

}
.text{
    max-width: 50%;
    text-align: left;
    flex: 1;
}

@media (max-width: 768px) {
    .descripcion {
        flex-direction: column;
    }

    .text {
        max-width: 100%;
    }
}

</style>



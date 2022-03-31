<template>
  <section class="product-cards--container">
        <Card nameLogo="clock" title="Tiempo Real" text="Nuestro API toma información minuto a minuto sobre las tasas que más determinan el comportamiento."/>
        <Card nameLogo="eye" title="No hay tasas escondidas" text="Ni en la compra o al momento de exit, Batabit siempre te muestra el costo real de lo que estás adquiriendo."/>
        <Card nameLogo="dollar" title="Compara monedas" text="No más rumores, con Batatabit sabrás el valor real de cada moneda en el mercado actual."/>
        <Card nameLogo="check" title="Información confiable" text="Nuestras fuentes están 100% verificadas y continuamos auditando su contenido mientras se actualizan."/>
  </section>
</template>

<script>
import Card from '@/components/CardDetail.vue'

export default {
    components : {
        Card,
    }

}
</script>

<style>

</style>
<template>
  <div class="plans--title">
      <h2>Escoge el plan que mejor se ajuste a ti.</h2>
      <p>Cualquier plan te da acceso completo a nuesta plataforma.</p>
  </div>
  <section class="plans-container--slider">
      <CardPlan title="Pago Mensual" price="30" description="*Ahorras $5 compranndo al plan semanal" :isRecomend="false"/>
      <CardPlan title="Pago Anual" price="99" description="*Ahorras $129 compranndo al plan mensual" :isRecomend="true"/>
      <CardPlan title="Pago Semanal" price="15" description="*Mejor precio del mercado" :isRecomend="false"/>
  </section>
</template>

<script>
import CardPlan from '@/components/CardPlan.vue'

export default {
    components : {
        CardPlan,
    }
}
</script>

<style>
:root{
    --black: #282623;
    --black-solf: #201e1c;
}

.plans--title {
    width: 90%;
    min-width: 288px;
    height: auto;
    margin: 0 auto;
    margin-bottom: 30px;
}

.plans--title h2 {
    padding-top: 50px;
    font-size: 2.4rem;
    font-weight: bold;
    line-height: 2.6rem;
    color: var(--black);
}

.plans--title p {
    padding: 30px;
    font-size: 1.4rem;
    font-weight: 500;
    line-height: 1.8rem;
    color: #757575;
}

.plans-container--slider {
    display: flex;
    gap: 5px;
    height: 316px;
    overflow-x: scroll;
    overscroll-behavior-x: contain;
    scroll-snap-type: x proximity;
}

.plans-container--slider::-webkit-scrollbar {
    width: 3px;
    height: 3px;
}

.plans-container--slider::-webkit-scrollbar-thumb{
    background: var(--black-solf);
    border-radius: 5px;
}

@media screen and (min-width: 930px){
    .plans-container--slider{
        justify-content: center;
    }
}
</style>
<template>
  <header>
    <Icon
      class="firts-icon"
      :source="headerInfo.icon"
      :altText="headerInfo.alt"
      classImg="header-icon"
    />
    <div class="header-title-container">
      <Paragraph
        text="La próxima revolución en el intercambio de criptomonedas."
        classSize="size-one-24rem"
        class="h2"
      />
      <Paragraph
        text="Patacoin te ayuda a navegar entre los diferentes precios y tendencias."
        classSize="size-two-14rem"
        class="p"
      />
      <a href="#plans" class="header--button"
        >Conoce Nuestros Planes <span class="arrow-button"></span
      ></a>
    </div>
  </header>
  <main>
    <section class="main-exchange-container">
      <div class="background-img"></div>
      <div class="main-exchange-container--title">
        <Paragraph
          text="Visibilizamos todas las tasas de cambio."
          classSize="size-one-24rem"
          class="h2"
        />
        <Paragraph
          text="Traemos información en tiempo real de las casas de cambio y las monedas más importantes del mundo."
          classSize="size-two-14rem"
          class="p"
        />
      </div>
      <Table />
    </section>
    <section class="main-product-detail">
      <span class="product-detail--logo"></span>
      <div class="product-detail--title">
        <h2>Creamos un producto sin comparación</h2>
        <p>Confiable y diseñado para su usuo diario.</p>
      </div>
      <Cards />
    </section>
    <section class="bitcoin-img-background">
      <h2>Conócelo hoy.</h2>
    </section>
    <section id="plans" class="main-plans-container">
      <Plans />
    </section>
    <footer>
      <FooterC />
    </footer>
  </main>
</template>

<script>
/* Components */
import Icon from "@/components/Icon.vue";
import Paragraph from "@/components/Paragraph.vue";
import Table from "@/components/Table.vue";
import Cards from "@/views/Cards.vue"
import Plans from "@/views/Plans.vue"
import FooterC from "@/views/Footer.vue"

/* Img and Icons */
import headerIcon from "@/assets/images/logo.svg";

export default {
  name: "App",
  data() {
    return {
      headerInfo: {
        icon: headerIcon,
        alt: "Icon page",
      },
    };
  },
  components: {
    Icon,
    Paragraph,
    Table,
    Cards,
    Plans,
    FooterC,
  },
};
</script>

<style>
:root {
  /* colores */
  --orange-hard: #f7931a;
  --orange-soft: #ffe9d5;
  --gray-soft: #90a19d;
  --blue-green: #196774;
  --black-solf: #201e1c;
  --just-white: #ffffff;
  --off-white: #faf8f7;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 62.5%;
  font-family: "DM Sans", sans-serif;
  /* background-color: var(--off-white); */
}

header {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  min-width: 320px;
  height: 334px;
  text-align: center;
  background: linear-gradient(207.8deg, #201e1c 16.69%, #f7931a 100%);
}

.header-title-container {
  width: 90%;
  min-width: 288px;
  max-width: 900px;
  height: 218px;
  margin-top: 40px;
  text-align: center;
  align-self: center;
}

.header-title-container .h1 {
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--just-white);
}

.h2 {
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--black-solf);
}

.header-title-container p {
  margin-top: 25px;
  line-height: 1.8rem;
  font-weight: 500;
  color: var(--orange-soft);
}

.header-title-container .header--button {
  position: absolute;
  left: calc(50% - 114.5px);
  top: 270px;
  display: block;
  margin-top: 35px;
  padding: 15px;
  width: 229px;
  height: 48px;
  background-color: var(--just-white);
  box-shadow: 0px 5px 10px rgba(89, 73, 39, 0.2);
  border: none;
  border-radius: 10px;
  font-size: 1.4rem;
  font-weight: bold;
  text-decoration: none;
  color: var(--black-solf);
}

.header-title-container .header--button span {
  display: inline-block;
  width: 13px;
  height: 8px;
  margin-left: 8px;
  background-image: url(./assets/icons/Vector.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

main {
  width: 100%;
  height: auto;
  background-color: var(--off-white);
}

.main-exchange-container {
  width: 90%;
  min-width: 288px;
  max-width: 900px;
  margin: 0 auto;
}

.main-exchange-container--title {
  width: 90%;
  min-width: 288px;
  max-width: 900px;
  margin: 0 auto;
}

.main-exchange-container .background-img {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  margin-bottom: 50px;
  background-image: url(./assets/images/bitcoin.svg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.main-exchange-container .h2 {
  text-align: center;
  margin-bottom: 30px;
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--black-solf);
}

.main-exchange-container .p {
  margin-bottom: 30px;
  font-size: 1.4rem;
  font-weight: 500;
  line-height: 1.6rem;
  text-align: center;
  color: #757575;
}

.main-product-detail {
  position: relative;
  width: 100%;
  min-width: 320px;
  height: auto;
  padding: 20px 10px;
  background-color: var(--black-solf);
}

.product-detail--logo {
  display: inline-block;
  position: relative;
  width: 40px;
  height: 25px;
  top: -33px;
  left: calc(50% - 20px);
  background-image: url(./assets/icons/icon.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.product-detail--title {
  width: 90%;
  min-width: 288px;
  height: auto;
  margin: 0 auto;
  margin-top: 50px;
  text-align: center;
}

.product-detail--title h2 {
  margin-bottom: 20px;
  font-size: 2.4rem;
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--just-white)
}

.product-detail--title p {
  margin-bottom: 30px;
  font-size: 1.4rem;
  font-weight: 500;
  line-height: 1.8rem;
  color: #808080;
}

.bitcoin-img-background {
  width: 100%;
  min-width: 320px;
  height: 50vh;
  background-image: url(./assets/images/bitcoinbabyx2.png);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  text-align: center;
}

.bitcoin-img-background h2{
  padding-top: 60px;
  font-size: 2.4rem;
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--just-white);
}

.main-plans-container {
  width: 100%;
  min-width: 320px;
  padding-bottom: 70px;
  text-align: center;
}

footer {
  display: flex;
  width: 100%;
  height: 150px;
  background-color: var(--orange-hard);
}
</style>

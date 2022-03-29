<template>
  <header>
    <Icon class="firts-icon"
      :source="headerInfo.icon"
      :altText="headerInfo.alt"
      classImg="header-icon"
    />
    <div class="header-title-container">
      <Paragraph text="La próxima revolución en el intercambio de criptomonedas." classSize="size-one-24rem" class="h1" />
      <Paragraph text="Patacoin te ayuda a navegar entre los diferentes precios y tendencias." classSize="size-two-14rem" class="p" />
    </div>
  </header>
</template>

<script>
/* Components */
import Icon from "@/components/Icon.vue";
import Paragraph from '@/components/Paragraph.vue'

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
  },
};
</script>

<style>
:root {
  /* colores */
  --orange-hard: #ef6024;
  --orange-soft: #f0941f;
  --gray-soft: #90a19d;
  --blue-green: #196774;
  --black-solf: #363432;
  --just-white : #ffffff;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 62.5%;
  font-family: "DM Sans", sans-serif;
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
  background: rgb(54,52,50);
  background: linear-gradient(90deg, var(--black-solf) 16%, var(--orange-hard) 100%);
}

.header-title-container{
  width: 90%;
  min-width: 288px;
  max-width: 900px;
  height: 218px;
  margin-top: 40px;
  text-align: center;
  align-self: center;
}

.header-title-container .h1{
  font-weight: bold;
  line-height: 2.6rem;
  color: var(--just-white);
}

.header-title-container p{
  margin-top: 25px;
  line-height: 1.8rem;
  font-weight: 500;
  color: var(--orange-soft);
}
</style>

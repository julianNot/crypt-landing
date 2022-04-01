<template>
  <article class="plans-container--card">
      <p v-show="isRecomend" class="recomended">Recomendado</p>
      <div class="plan-info-container">
          <h3 class="plan-card--title">{{title}}</h3>
          <p class="plan-card--price"> <span>$</span> {{price}}</p>
          <p class="plan-card--saving">{{description}}</p>
          <button class="plan-card-ca">Escoger Este <span></span></button>
      </div>
  </article>
</template>

<script>
export default {
    props : {
        title : String,
        price : Number,
        description : String,
        isRecomend : Boolean
    }
};
</script>

<style>
:root {
    --just-white: #ffffff;
    --bitcoin-orange: #f7931a;
    --black: #282623;
}

.plans-container--card {
    position: relative;
    scroll-snap-align: center;
    width: 70%;
    min-width: 230px;
    max-width: 300px;
    height: 250px;
    margin: 50px 15px 0;
    padding: 0 15px;
    background-color: var(--just-white);
    border-radius: 15px;
    box-shadow: 0 4px 8px rgba(89, 73, 30, 0.16);
}

.recomended {
    position: absolute;
    width: 120px;
    height: 31px;
    padding: 6px;
    margin-top: -15px;
    left: calc(50% - 60px);
    font-size: 1.2rem;
    font-weight: bold;
    background-color: var(--bitcoin-orange);
    border-radius: 8px;
    color: var(--just-white);
}

.plan-card--title {
    padding-top: 30px;
    font-size: 1.4rem;
    font-weight: 500;
    line-height: 1.8rem;
    color: black;
}

.plan-card--price {
    padding: 5px 0;
    font-size: 5.3rem;
    font-weight: 5.3rem;
    color: black;
}

.plan-card--price span{
    font-size: 1.2rem;
    font-weight: 300;
    position: absolute;
    margin-top: 10px;
    margin-left: -10px;
}

.plan-card--saving {
    font-size: 1.2rem;
    line-height: 1.5rem;
    width: 90%;
    margin: 0 auto;
    color: #757575;
}

.plan-card-ca {
    width: 150px;
    height: 48px;
    margin-top: 20px;
    background-color: #faf8f7;
    border: 2px solid var(--bitcoin-orange);
    border-radius: 4px;
    font-weight: bold;
    line-height: 1.8rem;
    color: var(--black);
}

.plan-card-ca span {
    display: inline-block;
    width: 20px;
    height: 20px;
    background-image: url(../assets/icons/arrow-right.svg);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    vertical-align: text-bottom;
}
</style>
<template>
    <article class="product-detail-card">
      <span :class="nameLogo"></span>
      <p class="product--card-title">{{title}}</p>
      <p class="product--card-body">{{text}}</p>
    </article>
</template>

<script>
export default {
    props :{
        nameLogo : String,
        title : String,
        text : String
    }
};
</script>

<style>
:root{
    --black-card: #282623;
    --just-white: #ffffff;
}

.product-detail-card{
    width: 90%;
    min-width: 288px;
    max-width: 400px;
    min-height: 150px;
    margin: 15px auto;
    padding: 15px;
    background-color: var(--black-card);
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.16);
}

.product--card-title {
    margin-bottom: 15px;
    font-size: 1.8rem;
    font-weight: bold;
    line-height: 1.8rem;
    color: var(--just-white)
}

.product--card-body {
    font-size: 1.4rem;
    font-weight: 500;
    line-height: 1.8rem;
    color: #808080;
}

.product-detail-card .eye {
  display: inline-block;
  width: 22px;
  height: 16px;
  margin-bottom: 10px;
  background-image: url(../assets/icons/eye.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.product-detail-card .clock {
  display: inline-block;
  width: 20px;
  height: 20px;
  margin-bottom: 10px;
  background-image: url(../assets/icons/clock.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.product-detail-card .dollar {
  display: inline-block;
  width: 14px;
  height: 22px;
  margin-bottom: 10px;
  background-image: url(../assets/icons/dollar-sign.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.product-detail-card .check {
  display: inline-block;
  width: 20px;
  height: 20px;
  margin-bottom: 10px;
  background-image: url(../assets/icons/check-circle.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
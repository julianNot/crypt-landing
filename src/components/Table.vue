<template>
    <section class="main-table-container">
        <div class="main-currency-table">
            <p class="currency-table--title">Monedas</p>
            <div class="currency-table--container">
                <table>
                    <tr>
                        <td class="table__top-left">{{cryptOne.name}}</td>
                        <td class="table__top-right table__right">{{cryptOne.current_price}} <span :class="isUp(cryptOne.price_change_percentage_24h)"></span></td>
                    </tr>
                    <tr>
                        <td>{{cryptTwo.name}}</td>
                        <td class="table__right">{{cryptTwo.current_price}} <span :class="isUp(cryptTwo.price_change_percentage_24h)"></span></td>
                    </tr>
                    <tr>
                        <td>{{cryptThree.name}}</td>
                        <td class="table__right">{{cryptThree.current_price}} <span :class="isUp(cryptThree.price_change_percentage_24h)"></span></td>
                    </tr>
                    <tr>
                        <td class="table__bottom-left">{{cryptFour.name}}</td>
                        <td class="table__bottom-right table__right">{{cryptFour.current_price}} <span :class="isUp(cryptFour.price_change_percentage_24h)"></span></td>
                    </tr>
                </table>
            </div>
            <div class="currency-table--date">
                <p><b>Actualizado:</b> {{date}}</p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data(){
        return{
            crypts : [],
            cryptOne : Object,
            cryptTwo : Object,
            cryptThree : Object,
            cryptFour : Object,
            date : null
        }
    },
    methods : {
        async getCrypts(){
            await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=4&page=1&sparkline=false').then(resp => resp.json())
            .then(data => {
                console.log(data);
                this.crypts.push(data)
                this.cryptOne = data[0]
                this.cryptTwo = data[1]
                this.cryptThree = data[2]
                this.cryptFour = data[3]
            } )
        },
        isUp(percentaje){
            if(percentaje > 0){
                return "up"
            }else{
                return "down"
            }
        }
    },
    beforeMount() {
        let tmpMls = Date.now()
        this.date = new Date(tmpMls).toLocaleTimeString()
        return this.getCrypts()
    }
}
</script>

<style scoped>
:root{
    --orange-soft: #ffe9d5;
    --black-solf: #201e1c;
}

.main-currency-table{
    width: 70%;
    min-width: 235px;
    max-width: 500px;
    height: 360px;
    margin: 0 auto;
    text-align: center;
}

.main-currency-table .currency-table--title{
    margin-bottom: 15px;
    font-size: 1.8rem;
    line-height: 2.3rem;
    font-weight: 700;
    color: #ff9536;
}

.currency-table--container {
    width: 90%;
    min-width: 230px;
    max-width: 300px;
    height: 250px;
    margin: 0 auto;
}

.currency-table--container table{
    width: 100%;
    height: 100%;
}

.currency-table--container td {
    width: 50%;
    font-size: 1.6rem;
    font-weight: 500;
    line-height: 1.9rem;
    color: #90a19d;
    background-color: #ffffff;
}

.currency-table--container .table__top-left{
    border-radius: 15px 0 0 0;
}

.currency-table--container .table__top-right{
    border-radius: 0 15px 0 0;
}

.currency-table--container .table__bottom-left {
  border-radius: 0 0 0 15px;
}

.currency-table--container .table__bottom-right {
  border-radius: 0 0 15px 0;
}

.currency-table--container .table__right{
    font-size: 1.4rem;
    font-weight: normal;
    line-height: 1.7rem;
    color: #757575;
}

.currency-table--date{
    width: 190px;
    height: 30px;
    margin: 0 auto;
    margin-top: 15px;
    padding: 8px;
    background-color: var(--orange-soft);
    border-radius: 8px;
}

span{
    margin-right: 10px;
    vertical-align: text-bottom;
}
.up {
  display: inline-block;
  width: 20px;
  height: 20px;
  background-image: url(../assets/icons/trending-up.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.down {
  display: inline-block;
  width: 20px;
  height: 20px;
  background-image: url(../assets/icons/trending-down.svg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  /* vertical-align: text-bottom; */
}

.currency-table--date p {
  font-size: 1.2rem;
  line-height: 1.5rem;
  font-weight: 300;
  color: var(--black-solf);
}
</style>
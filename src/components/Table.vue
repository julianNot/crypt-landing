<template>
    <section class="main-table-container">
        <div class="main-currency-table">
            <p class="currency-table--title">Monedas</p>
            <div class="currency-table--container">
                <table>
                    <tr>
                        <td class="table__top-left">name</td>
                        <td class="table__top-right table__right">price</td>
                    </tr>
                    <tr>
                        <td>Name1</td>
                        <td class="table__right">price</td>
                    </tr>
                    <tr>
                        <td>Name2</td>
                        <td class="table__right">price</td>
                    </tr>
                    <tr>
                        <td class="table__bottom-left">Name3</td>
                        <td class="table__bottom-right table__right">Price</td>
                    </tr>
                </table>
            </div>
            <div class="currency-table--date">
                <p><b>Actualizado:</b> Fecha</p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data(){
        return{
            crypts : [],
            endList : Number
        }
    },
    methods : {
        async getCrypts(){
            await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=4&page=1&sparkline=false').then(resp => resp.json())
            /* .then(data => console.table(data) *//* {
                const {crypt1, crypt2, crypt3, crypt4} = data
                console.log(data);
                this.crypts.push(crypt1)
                this.crypts.push(crypt2)
                this.crypts.push(crypt3)
                this.crypts.push(crypt4)
            } )*/
        },
        mounted() {
            return console.log(this.getCrypts())
        },
    },
}
</script>

<style>
:root{
    --soft-orange: #ffe9d5;
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
    background-color: var(--soft-orange);
    border-radius: 8px;
}
</style>
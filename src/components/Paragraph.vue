<template >
  <p :class="classSize">{{text}}</p>
</template>

<script>
export default {
    props : {
        text : String,
        classSize : String
    }
}
</script>

<style>
.size-one-24rem{
    font-size: 2.4rem;
}

.size-two-14rem{
    font-size: 1.4rem;
}

.size-trhee-12rem{
    font-size: 1.2rem;
}

</style>
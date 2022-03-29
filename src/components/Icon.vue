<template>
  <img :src="source" :alt="altText" :class="classImg">
</template>

<script>
export default {    
    props : {
        source : String,
        altText : String,
        classImg : String
    }
}
</script>

<style scoped>
.header-icon{
    width: 150px;
    height: 24px;
    margin-top: 60px;
    align-self: center;
}
</style>
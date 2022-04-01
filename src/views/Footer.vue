<template>
  <section class="left">
      <ul>
          <li><a target="_blank" href="https://www.linkedin.com/in/julian-ardila404/">Linkedin</a></li>
          <li><a target="_blank" href="https://github.com/julianNot">Github</a></li>
          <li><a target="_blank" href="https://twitter.com/julianNotDev">Twitter</a></li>
      </ul>
  </section>
  <section class="right">
      <img src="../assets/images/logo-footer.svg" alt="Logo page 2022">
  </section>
</template>

<script>
export default {

}
</script>

<style scoped>
:root {
    --just-white: #ffffff
}

section {
    display: flex;
    width: 50%;
    justify-content: center;
    align-items: center;
}

.left ul {
    font-size: 1.4rem;
    font-weight: 500px;
    line-height: 1.8rem;
    list-style: none;
}

.left li {
    margin: 10px 0;
}

.left a {
    text-decoration: none;
    color: var(--just-white);
}
</style>
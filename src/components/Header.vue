<template>
  <header class="header">
      <img src="../assets/img/logo.png" :alt="headerLogo.text">
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            headerLogo: {
                img: '../assets/img/logo.png',
                text: 'Spotify Logo Header'
            },
        }
    }
}
</script>

<style scoped lang="scss">

.header {
    padding: .3rem;
    background: #2e3a46;
}

.header img {
    max-width: 50px;
}

</style>
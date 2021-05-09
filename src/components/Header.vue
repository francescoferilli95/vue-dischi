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
@import '@/styles/vars';
.header {
    padding: $header-padding;
    background: $bg-header-color;
}

.header img {
    max-width: $header-img-width;
}

</style>
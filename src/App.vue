<template>
  <div id="app">
  <!-- HEADER -->
  <Header />
  <!-- CONTENT -->
  <Content /> 
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Content from '@/components/Content.vue';

export default {
  name: "App",
  components: {
    Header,
    Content,
  },
};
</script>

<style lang="scss">

// FONTS
@import "~@fontsource/montserrat/index.css";
@import "~@fontsource/montserrat/700.css";

@import '@/styles/general';
</style>

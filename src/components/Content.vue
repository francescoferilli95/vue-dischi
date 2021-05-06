<template>
  <main class="content">
      <Cards />
  </main>
</template>

<script>
import Cards from '@/components/Cards.vue';

export default {
    name: 'Content',
    components: {
        Cards,
    }
}
</script>

<style scoped lang="scss">

.content {
    background:  #1d2d3c;
    height: calc(100vh - 64px);
}

</style>
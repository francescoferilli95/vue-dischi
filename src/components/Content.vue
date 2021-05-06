<template>
  <main class="content">
    <div v-for="(card, index) in musicCards" :key="index" class="cardList">
      <Cards :details="card" />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Cards from '@/components/Cards.vue';

export default {
    name: 'Content',
    components: {
        Cards,
    },
    data () {
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            musicCards: [],
            loading: true,
        }
    },
    created() {
        this.getMusicCard();
    },
    methods: {
        getMusicCard() {
            /**
             * API CALL
             */
            axios.get(this.apiURL)
                // SUCCESS
                .then(res => {
                    this.musicCards = res.data.response;
                    console.log(this.musicCards);
                    this.loading = false;
                })
                // FAIL
                .catch( err => {
                    console.log('Error', err);
                    alert('Error',err);
                });
        },
    },
}
</script>

<style scoped lang="scss">

.content {
    display: flex;
    flex-wrap: wrap;
    padding-top: 100px;
    background:  #1d2d3c;
    height: calc(100vh - 64px);
}

.cardList:nth-child(9),
.cardList:nth-child(10) {
    position: relative;
    left: 36.6%;
}

</style>
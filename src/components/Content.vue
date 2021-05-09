<template>
  <main class="content">
      <div>
          <FilterMusic @changed="filteredGenre" />
      </div>
    <div v-for="(card, index) in newMusicList" :key="index" class="cardList">
      <Cards :details="card" />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Cards from '@/components/Cards.vue';
import FilterMusic from '@/components/FilterMusic.vue';

export default {
    name: 'Content',
    components: {
        Cards,
        FilterMusic
    },
    data () {
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            musicCards: [],
            loading: true,
            genreSelected: 'all',
        }
    },
    computed: {
        newMusicList() {
            if (this.genreSelected === 'all') {
                return this.musicCards;
            }
            return this.musicCards.filter( el => { return el.genre.toLowerCase() === this.genreSelected.ToLowerCase();})
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
    filteredGenre(select) {
        this.genreSelected = select;
        console.log(this.genreSelected);
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

</style>
<template>
    <div class="card">
    <img :src="details.poster" :alt="details.title">
    <h2>{{details.title}}</h2>
    <h3>{{details.author}}</h3>  
    <h3>{{details.year}}</h3>
    <h4>{{details.genre}}</h4> 
    </div>
</template>

<script>
export default {
    name: 'Cards',
    props: ['details'],
}
</script>

<style scoped lang="scss">

.card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 200px;
    height: 300px;
    flex-basis: calc(100% / 8);
    background: #2e3a46;
    margin: 0 1rem;
    padding: 1rem;
}

.card img {
    max-width: 150px;
}

h2 {
    font-size: 18px;
    margin: 12px 0;
}

h3 {
    font-size: 16px;
    margin-bottom: 10px;
}

h4 {
    font-size: 14px;
}

</style>
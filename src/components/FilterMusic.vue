<template>
  <div class="filter">
      <label for="genre-select">Filter by genre:</label>
      <select name="genre" id="genre-select" v-model="selected" @change="$emit('changed', selected)">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
  </div>
</template>

<script>
export default {
    name: 'FilterMusic',
    data() {
        return {
            selected: 'all',
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/vars';

.filter {
    position: absolute;
    left: 50%;
    top: 12%;
    transform: translateX(-50%);
}

label {
    color: $text-primary-color;
    margin-right: $m-right;
    font-size: $fnt-size;
}

#select {
    width: 75px;
    padding: 5px;
    border-radius: 10px;
    border: none;
    outline: none;
    transition: background .3s;
}

#select:hover {
    background: rgb(170, 169, 169);
}

</style>
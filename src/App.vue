<template>
  <div class="container">
    <h1>Rick and Morty</h1>
    <filter-by-status />
    <filter-by-name />
    <list-characters />
  </div>
</template>

<script>
import FilterByName from './components/filterByName.vue'
import FilterByStatus from './components/filterByStatus.vue'
import ListCharacters from './components/listCharacters.vue'


export default {
  name: 'App',
  components: {
    ListCharacters,
    FilterByStatus,
    FilterByName
    
  }
}
</script>

<style lang="scss">
:root{
  --background-body: #24282f;
  --background-card: #3C3E44;
  --text-white: #fff;
  --text-gray: #c0c0c0;
  --text-orange: #ff9800;
}
body{
  background-color: var(--background-body);
  color: var(--text-white);
  font-family: 'Segeo UI',Verdana, Geneva, Tahoma, sans-serif;
}
h1{
  text-align: center;
  margin-bottom: 3rem;
}
.container{
  width: 980px;
  max-width: 90%;
  margin: 5rem auto;
}
img{
  width: 100%;
  max-height: 400px;
}
</style>

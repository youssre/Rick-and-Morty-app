<template>
  <div class="search">
      <input type="text" placeholder="Search by name" v-model="name" @keyup="filter()">
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
import { useStore } from 'vuex'
export default {
    setup(){
        const store = useStore();
        const name = ref('')
        const filter = (()=>{
            store.dispatch('filterByName', name.value)
        })

        return{
            name,
            filter
        }
    }
}
</script>

<style lang="scss">
.search{
    width: 80%;
    margin: 3rem auto 0px;
    
    input{
        height: 53px;
        width: 100%;
        border: none;
        border-radius: 10px;
        padding: 0 0.5rem;
        font-size: 21px;
        
        
        &:focus{
            outline: none;
            box-shadow: 0 0 10px dodgerblue;
        }
    }
}
</style>
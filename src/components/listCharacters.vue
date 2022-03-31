<template>
    <div class="characters">
        <div class="characters-item" v-for="character in characters" :key="character.id">
            <card-character :character="character"/>
        </div>
    </div>
</template>

<script>
import { computed, onMounted } from 'vue';
import { useStore } from "vuex"
import CardCharacter from './cardCharacter.vue';
export default {
    components: {
        CardCharacter
    },
    setup() {
        const store = useStore();
        const characters = computed(()=> {
            return store.state.charactersFilter
        })
        onMounted(()=> {
            store.dispatch('getCharacters');
        })

        return{
            characters
        }
    }
}
</script>

<style>
.characters{
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    flex-grow: inherit;
    gap: 3rem;
    align-items: center;
    margin: 3rem 0;
}
</style>
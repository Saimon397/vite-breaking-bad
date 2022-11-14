<template>
    <div class="cards-container">
        <div v-html="`found ${characterList.length} characters...`" class="bg-dark p-3 text-uppercase text-white"></div>
        <CardsComponent :character="characterList" />
    </div>
</template>

<script>
import axios from 'axios'
import CardsComponent from './CardsComponent.vue';

export default {
    components: {
        CardsComponent,
    }, data() {
        return {
            apiURL: 'https://www.breakingbadapi.com/api/characters',
            characterList: [],
            loading: false
        }
    },
    methods: {
        getCharacters() {
            axios.get(this.apiURL).then(
                (res) => {
                    this.characterList = [...res.data]
                    console.log(this.characterList)
                },
            )
                .catch((error) => {
                    console.log(error);
                })
        }
    },
    created() {
        this.getCharacters()
    }
}
</script>

<style lang="scss" scoped>

</style>
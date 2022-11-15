<template>
    <CategoryComponent @filterchar="getCharacters" />
    <div class="cards-container">
        <div v-html="`found ${characterList.length} characters...`"
            class="text-center border bg-dark p-3 text-uppercase text-white"></div>
        <CardsComponent :character="characterList" :loading="loading" />
    </div>
</template>

<script>
import axios from 'axios'
import CardsComponent from './CardsComponent.vue';
import CategoryComponent from './CategoryComponent.vue';

export default {
    components: {
        CardsComponent,
        CategoryComponent,
    }, data() {
        return {
            apiURL: 'https://www.breakingbadapi.com/api/characters',
            characterList: [],
            loading: false
        }
    },
    methods: {
        getCharacters(category) {
            let options = null
            if (category) {
                options = {
                    params: {
                        category: category
                    }
                }
            }
            axios.get(this.apiURL, options).then(
                (res) => {
                    this.characterList = [...res.data]
                    console.log(this.characterList)
                    this.loading = false;
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
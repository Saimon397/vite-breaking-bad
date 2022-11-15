<template>
    <CategoryComponent @filterchar="getCharacters" />
    <div class="cards-container">
        <div v-html="`found ${store.characterList.length} characters...`"
            class="text-center border bg-dark p-3 text-uppercase text-white"></div>
        <CardsComponent :character="store.characterList" :loading="store.loading" />
    </div>
</template>

<script>
import axios from 'axios'
import CardsComponent from './CardsComponent.vue';
import CategoryComponent from './CategoryComponent.vue';
import { store } from '../store';

export default {
    components: {
        CardsComponent,
        CategoryComponent,
    }, data() {
        return {
            store
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
            axios.get(store.apiURL, options).then(
                (res) => {
                    store.characterList = [...res.data]
                    console.log(store.characterList)
                    store.loading = false;
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
<template>
    <form class="form-floating bg-dark col-2 pt-0 w-100 d-flex justify-content-end" @submit.prevent='searchcharater'>
        <select class="form-select pt-0 pb-0 fs-4 bg-dark text-white text-center w-75" id="inlineFormSelectPref"
            v-model="search">
            <option selected value="">Select Category:</option>
            <option :value="category" v-for="(category, index) in StatusOptions" :key="index">{{ category }}</option>
        </select>
        <button type="search" class="w-50 border btn btn-success text-uppercase fw-bold">Search</button>
        <button type="reset" class="w-50 border btn btn-danger text-uppercase fw-bold"
            @click="resetsearch">Reset</button>
    </form>
</template>

<script>
export default {
    name: 'CategoryComponent',
    data() {
        return {
            StatusOptions: [
                'Breaking Bad',
                'Better Call Saul'],
            search: '',
        }
    },
    methods: {
        searchcharater() {
            this.$emit('filterchar', this.search)
            console.log(this.search)
        },
        resetsearch() {
            this.search = '',
                this.$emit('filterchar', this.search)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
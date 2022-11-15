<template>
  <div class="container">
    <div class="d-flex justify-content-center row">
      <div class="col-2 m-3 p-3 text-center bg-dark border rounded-2" v-for="(item) in character " :key="item.char_id">
        <img :src="item.img" :alt="item.name">
        <h4 class="mt-3 text-white">{{ item.name }}</h4>
        <h6 class="text-secondary">{{ item.category }}</h6>
        <p class="text-secondary">{{ item.status }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardsComponent',
  props: [
    'character'
  ],
}
</script>

<style lang="scss" scoped>

</style>

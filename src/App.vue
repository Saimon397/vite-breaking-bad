<template>
  <div>
    <HeaderComponent />
    <MainComponent />
    <FooterComponent />
  </div>
</template>

<script>
import FooterComponent from './components/FooterComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import CategoryComponent from './components/CategoryComponent.vue';

export default {
  components: { HeaderComponent, MainComponent, FooterComponent, CategoryComponent }
}
</script>

<style lang="scss" scoped>

</style>
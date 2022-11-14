<template>
  <div>
    <nav class="navbar">
      <div class="container-fluid">
        <a class="navbar-brand fs-1 text-white" href="#nogo">
          <img src="/img/imgbin_logo-breaking-bad-png.png" width="100" alt="Logo"
            class="d-inline-block fe-1 align-text-top">
          Breaking Bad Api
        </a>
        <div class="form-floating bg-dark col-2 pt-0">
          <select class="form-select pt-0 pb-0 fs-4 bg-dark text-white">
            <option selected>Select Category:</option>
            <option value="1">Alive</option>
            <option value="2">Deceased</option>
            <option value="3">Presumed dead</option>
          </select>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'HeaderComponent',
}
</script>

<style lang="scss" scoped>

</style>
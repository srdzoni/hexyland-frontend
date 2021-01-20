<template>
  <div class="page">
    <AppHeader />
    <Nuxt />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from '~/components/core/AppHeader';
import AppFooter from '~/components/core/AppFooter';
export default {
  components: {
    AppFooter, AppHeader
  }
}
</script>

<style>
.page {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  /*background-image: var(--bg-img);*/
  background-repeat: no-repeat;
}
</style>

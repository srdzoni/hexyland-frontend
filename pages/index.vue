<template>
  <div class="content">
    <Hero />
    <Business :index-data='index' />
  </div>
</template>

<script>

import Hero from '~/components/index/Hero'
import Business from '~/components/index/Business'
export default {
  components: {
    Hero, Business
  },

  async asyncData({ $axios }) {
    const index = await $axios.$get(`/index`)
    return { index }
  }
}
</script>

<style>

</style>

<template>
  <span class="hero__brag-social-link"
    ><a
      :href='url'
      target="_blank"
    >
      <font-awesome-icon
        v-bind:style="{color: color, marginRight: 5 + 'px'}"
        :icon="['fab', network]"
      />LinkedIn</a
    ></span
  >
</template>

<script>
export default {
  name: 'HeroSocialLink',
  props: ['network', 'color', 'url'],
  computed: {
    style() {
      return "color: " + this.color + "; margin-right: 4px";
    }
  }
}
</script>

<style scoped>
.hero__brag-social-link {
  margin-right: 5px;
  padding: 3px;
}
</style>

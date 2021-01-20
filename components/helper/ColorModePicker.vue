<template>
  <button @click="toggleDarkMode()">
    <ColorScheme placeholder="..." tag="span">
      <span v-if="$colorMode.value === 'dark'">
        <font-awesome-icon :icon="['fas', 'sun']" class='fa-lg icon-light'/>
      </span>
      <span v-else>
        <font-awesome-icon :icon="['fas', 'moon']" class='fa-lg icon-dark'/>
      </span>
    </ColorScheme>
  </button>
</template>

<script>
import IconLight from '@/assets/icons/light.svg?inline'
import IconDark from '@/assets/icons/dark.svg?inline'

export default {
  name: 'ColorModePicker',

  components: {
    IconLight,
    IconDark
  },

  methods: {
    toggleDarkMode() {
      if (this.$colorMode.preference !== 'dark') {
        this.$colorMode.preference = 'dark'
      } else {
        this.$colorMode.preference = 'light'
      }
    }
  }

}
</script>

<style scoped>
  button {
    background-color: transparent;
    border: 1px solid var(--text-color-primary);
    background-color: var(--text-color-primary);
    border-radius: 50%;
    outline: none;
    transition: background-color .3s;
  }


  .icon-light {
    color: var(--bg-color-secondary);
  }

  .icon-dark {
    color: var(--bg-color-secondary);
  }
</style>

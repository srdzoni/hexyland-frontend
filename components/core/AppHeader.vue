<template>
  <div class="main-nav animated-bg">
    <div class="nav-item">
      <Logo />
    </div>

    <div class="nav-item">
      <nuxt-link to="/projects">projects</nuxt-link>
    </div>
    <div class="nav-item"><nuxt-link to="/blog">blog</nuxt-link></div>
    <div class="nav-item"><nuxt-link to="/misc">misc</nuxt-link></div>
    <div class="nav-item"><nuxt-link to="/about">about</nuxt-link></div>
    <div class="nav-item"><nuxt-link to="/contact">contact</nuxt-link></div>
    <ColorModePicker class="nav-item" />
  </div>
</template>

<script>
import Logo from '@/components/Logo';
import ColorModePicker from '@/components/helper/ColorModePicker'

export default {
  name: 'AppHeader',

  components: {
    Logo, ColorModePicker
  },
}
</script>

<style scoped>
.main-nav {
  background-color: var(--bg-color-secondary);
  /*color: #f05454;*/
  -webkit-box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.5);
  width: 100%;
  justify-content: space-between;
  align-items: center;
  display: flex;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
}

.nav-item {
  padding: 7px;
  margin: 0px;
  display: flex;
  font-weight: bold;
  max-height: 50px;
}

.nav-item:first-of-type {
  margin-right: auto;
}

.nav-item:last-of-type {
  margin: 0px 20px 0px 0px;
}

.animated-bg {
  background: linear-gradient(219deg, var(--bg-color-primary), var(--bg-color-secondary));
  background-size: 400% 400%;

  -webkit-animation: AnimationName 9s ease infinite;
  -moz-animation: AnimationName 9s ease infinite;
  -o-animation: AnimationName 9s ease infinite;
  animation: AnimationName 9s ease infinite;
}

@-webkit-keyframes AnimationName {
  0% {
    background-position: 0% 82%;
  }
  50% {
    background-position: 100% 19%;
  }
  100% {
    background-position: 0% 82%;
  }
}
@-moz-keyframes AnimationName {
  0% {
    background-position: 0% 82%;
  }
  50% {
    background-position: 100% 19%;
  }
  100% {
    background-position: 0% 82%;
  }
}
@-o-keyframes AnimationName {
  0% {
    background-position: 0% 82%;
  }
  50% {
    background-position: 100% 19%;
  }
  100% {
    background-position: 0% 82%;
  }
}
@keyframes AnimationName {
  0% {
    background-position: 0% 82%;
  }
  50% {
    background-position: 100% 19%;
  }
  100% {
    background-position: 0% 82%;
  }
}
</style>

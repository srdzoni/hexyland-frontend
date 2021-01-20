<template>
  <div class="hero">
    <div class="hero__brag">
      <div class="hero__brag-welcome"><h1>Hello and welcome!</h1></div>
      <div class="hero__brag-intro">
        <h2>
          My name is
          <GlitchText text='Srđan Đorđević' path-to='/about' />
          and this is my piece of the interwebz
        </h2>
        <br />
        I <span class="hero__brag-link"><nuxt-link to="/projects">code</nuxt-link></span
        >, <span class="hero__brag-link"><nuxt-link to="/blog">shitpost</nuxt-link></span> and
        build
        <span class="hero__brag-link"><nuxt-link to="/misc">stuff</nuxt-link></span>
      </div>
    </div>
    <div class="hero__social">

      <HeroSocialLink color='#2867b2' network='linkedin' url='https://www.linkedin.com/in/sr%C4%91an-%C4%91or%C4%91evi%C4%87-20bba7109/' />
      <HeroSocialLink color='#1da1f2' network='twitter' url='https://twitter.com/sergioushex' />
      <HeroSocialLink color='#888888' network='github' url='https://github.com/srdzoni' />

    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero',
}
</script>

<style scoped>
.hero {
  padding: 15px;
  flex-direction: column-reverse;
  justify-content: space-between;
  font-variation-settings: 'CASL' 0.5;
  font-variation-settings: 'wght' 600;
  /* background-image: url("../img/580b57fbd9996e24bc43bfa3.png"); */

  position: relative;
  /* border: 1px solid orange; */
  font-size: x-large;
}

/* .hero::after {
  content: "";
  background: url("../img/580b57fbd9996e24bc43bfa3.png");
  background-repeat: no-repeat;
  background-position: center;
  opacity: 0.06;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  z-index: -1;
} */

/* .hero div {
  border: 1px solid orange;
} */

.hero a:hover,
.hero a:visited:hover {
  border-bottom: none;
}

/* TBD


.hero a:link {
  color: #5995da;
  text-decoration: none;
}
.hero a:visited {
  color: #407fc7;
}
.hero a:hover,
.hero a:visited:hover {
  color: #76aeed;
  border-bottom: 1px solid #76aeed;
}
.hero a:active,
.hero a:visited:active {
  color: #5995da;
}

.hero a {
  background: -webkit-linear-gradient(#f0545480, #f05454);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

*/

.hero__brag {
  margin: 20px;
}

.hero__brag h1 {
  font-size: 60px;
}

.hero__social {
  display: flex;
  justify-content: left;
  align-items: center;
  margin: 20px;
}

</style>

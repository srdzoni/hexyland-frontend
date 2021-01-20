<template>
  <div class="footer">
    <div class="footer__subscribe">
      <input type="email" placeholder="your email" /><button>submit</button>
    </div>
    <div>
      <div>
        <div>
          Copyright &copy 2021
          <a href="#">srki.me</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppFooter',
}
</script>

<style scoped>
.footer {
  padding: 20px;
  width: 100%;
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: column;
}
</style>

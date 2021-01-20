<template>
  <div class='content'>
    <div class='blog-post-wrapper'>
      <div class='blog-post-title'>
        <h1>{{ post.title }}</h1>
        <h2>{{ post.description }}</h2>
      </div>
      <div class='blog-post-content'>
        <p v-html='post.plaintext'>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'index.vue',
  async asyncData({ $axios, route }) {
    const post = await $axios.$get('/post/' + route.params.post);
    return { post };
  },
}
</script>

<style scoped>

.blog-post-wrapper {
  /*color: #dddddd;*/
  margin: 15px;
  /*background-color: var(--bg-color-secondary);*/
  padding: 15px;
  border-radius: 10px;
  /*border-right: 5px solid var(--bg-color-secondary);*/
  /*border-right: 3px solid var(--bg-color-secondary);*/
  /*-webkit-box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);*/
  /*box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);*/
  /*font-family: var(--blog-post-font);*/
  /*font-weight: var(--blog-post-font-weight);*/
  /*font-stretch: var(--blog-post-font-width);*/
  /*font-variation-settings: "wght" var(--blog-post-font-weight);*/
  font-variation-settings: "CRSV" 1;
  font-variation-settings: "CASL" 0.2;
  text-justify: inter-ideograph;
}

.blog-post-wrapper p {
  font-variation-settings: "wght" var(--blog-post-font-weight);
  color: var(--text-color-secondary);
}

.blog-post-wrapper h1 {
  text-align: center;
  padding: 10px;
  width: 100%;
  border-bottom: 2px dashed var(--bg-color-secondary);
}

.blog-post-wrapper h2 {
  padding: 20px 0px 20px 0px;
}

.blog-post-title {

}

.blog-post-content {
  /*color: #eeeeee;*/
}

</style>

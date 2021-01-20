<template>
  <div class="content">
    <div class="blog-page__title"><h1>Blog posts</h1></div>
    <div class="blog-page__content-meta">
      <div class="blog-page__content-meta-categories">categories</div>
      <div class="blog-page__content-meta-tags">
        <TagChip v-for='tag in posts.tags' :title='tag.title' :slug='tag.slug' :key='tag.slug' />
      </div>
    </div>
    <div class="blog-page__content-posts">
      <div v-for='post in posts.posts' class='blog-page__content-post'>
        <div class='blog-page__content-post-timestamp'>
          {{ timestampToDate(post.timestamp) }}
        </div>
        <div class='blog-page__content-post-title'>
          <div class='blog-page__content-post-link'>
            <nuxt-link :to="`/blog/category/${post.categorySlug}`">{{ post.category }}</nuxt-link> &gt; <nuxt-link :to="`/blog/${post.slug}`">{{ post.title }}</nuxt-link>
          </div>
          <div class='blog-page__content-post-tags'>
            <span class="blog-page__content-post-tag" v-for='t in posts.tags'>#{{ t.title }}</span>
          </div>
        </div>

      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'index.html',

  async asyncData({ $axios }) {
    const posts = await $axios.$get(`/posts`)
    return { posts }
  },

  methods: {
    timestampToDate(timestamp) {
      return new Date(parseInt(timestamp)).toLocaleDateString("en-GB")
    }
  }
}
</script>

<style scoped>


.blog-page__title {
  margin: 15px;
}

.blog-page__content-posts {
  margin: 15px;

}

.blog-page__content-post {
  display: flex;
  padding-bottom: 15px;
}

.blog-page__content-post-timestamp {
  min-width: 150px;
  margin-left: 0;
  margin-right: auto;
  text-align: right;
  align-content: baseline;
  padding: 3px 16px 3px 10px;
}

.blog-page__content-post-link {

  align-content: baseline;
  padding: 3px 16px 3px 10px;
}

.blog-page__content-post-title {
  width: 100%;
}

.blog-page__content-post-tags {
  color: var(--text-color-tertiary);
  padding-left: 10px;
  font-size: smaller;
}
.blog-page__content-meta {
}

.blog-page__content-meta-categories {
}

.blog-page__content-meta-tags {
  display: flex;
  margin: 15px;
}
</style>

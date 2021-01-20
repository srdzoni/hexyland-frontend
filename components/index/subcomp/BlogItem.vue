<template>
  <div class="blog__posts-item">
    <div class="blog__posts-item-header">
      <div class="blog__posts-item-title">
        <h4>
          <font-awesome-icon :icon="['fas', 'paragraph']" class='blog__posts-item-paragraph'/><nuxt-link :to="`/blog/category/${this.categorySlug}`">{{ category }}</nuxt-link> &gt; <nuxt-link :to="`/blog/${this.slug}`">{{ title }}</nuxt-link>
        </h4>
      </div>
      <div class="blog__posts-item-date">{{ timestampToDate }}</div>
    </div>
    <div class="blog__posts-item-desc">
      <p>
        {{ description }}
<!--        <span><nuxt-link :to="`/blog/${this.slug}`">(read more)</nuxt-link></span>-->
      </p>
    </div>
    <div class='blog__posts-item-footer'>
      <span class='blog__posts-item-footer-tag' v-for='tag in tags'><nuxt-link :to="`/blog/tag/${tag}`">#{{ tag }}</nuxt-link></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogItem',
  props: ["category", "title", "timestamp", "description", "slug", "categorySlug", "tags"],

  computed: {
    timestampToDate() {
      return new Date(parseInt(this.timestamp)).toLocaleDateString("en-GB")
    }
  }
}
</script>

<style scoped>
.blog__posts-item {
  margin: 5px 0px 15px 0px;
  padding: 10px 10px 0px 10px;
  border-radius: 5px;

  border-left: 3px solid var(--bg-color-secondary);
  border-bottom: 3px solid var(--bg-color-secondary);
}

.blog__posts-item:hover {
  /*background-image: url('~assets/img/coffee-blog-bg.png');*/
  /*background-repeat: no-repeat;*/
  /*background-position: top right;*/
  background-color: var(--bg-color-secondary);
  -webkit-box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);

}

.blog__posts-item:hover .blog__posts-item-desc {
  border-bottom: 1px dashed var(--bg-color-primary);
}

/*.blog__posts-item a {*/
/*  color: #dddddd;*/
/*}*/


/*.blog__posts-item a:hover {*/
/*  color: #ffffff;*/
/*}*/

.blog__posts-item:last-of-type {
  margin-bottom: 0px;
}

.blog__posts-item-header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.blog__posts-item-title {
}

.blog__posts-item-date {
  font-size: small;
  color: var(--text-color-tertiary);
  white-space: nowrap;
}

.blog__posts-item-desc {
  width: 100%;
  margin: 10px 0px 5px 0px;
  color: var(--text-color-secondary);
  border-bottom: 1px dashed var(--bg-color-secondary);
  padding-bottom: 5px;
}

.blog__posts-item-desc:hover {
  border-bottom: 1px dashed var(--bg-color-primary);
}

.blog__posts-item-paragraph {
  /*color: #888888;*/
  margin-right: 7px;
  /*box-shadow: var(--shadow-color);*/
}

.blog__posts-item-footer {
  display: flex;
  align-items: baseline;
  justify-content: flex-end;
  width: 100%;
  height: 20px;
  flex-direction: row;
}

.blog__posts-item-footer-tag {
  padding-right: 7px;
  color: var(--text-color-tertiary);
  font-size: small;
  font-variation-settings: "slnt" -10;

}

</style>

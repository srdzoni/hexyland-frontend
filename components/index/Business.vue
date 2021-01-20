<template>
  <div>
    <div class="business">
      <div class="projects subcontainer">
        <div class="subcontainer-title">
          <nuxt-link to="/projects"><h3>from my lab</h3></nuxt-link>
        </div>
        <div class="subcontainer-content">





          <ProjectItem
            title="AlcOS"
            slug="alcos-operativni-sistem"
            description="Etiam tincidunt mi nisl, at dictum dolor bibendum non. Fusce
              molestie et massa vulputate iaculis. Vestibulum ante ipsum primis
              in faucibus orci luctus et ultrices posuere cubilia curae"
            github-url="https://www.github.com/alcos"
            percent-done="100"
            :tech="['java', 'vuejs', 'html']"
          />
          <ProjectItem
            title="AlcOS"
            slug="alcos-operativni-sistem"
            description="Etiam tincidunt mi nisl, at dictum dolor bibendum non. Fusce
              molestie et massa vulputate iaculis. Vestibulum ante ipsum primis
              in faucibus orci luctus et ultrices posuere cubilia curae"
            github-url="https://www.github.com/alcos"
            percent-done="87"
            :tech="['java', 'vuejs', 'html']"
          />
          <ProjectItem
            title="AlcOS"
            slug="alcos-operativni-sistem"
            description="Etiam tincidunt mi nisl, at dictum dolor bibendum non. Fusce
              molestie et massa vulputate iaculis. Vestibulum ante ipsum primis
              in faucibus orci luctus et ultrices posuere cubilia curae"
            github-url="https://www.github.com/alcos"
            percent-done="17"
            :tech="['java', 'vuejs', 'html']"
          />
          <ProjectItem
            title="AlcOS"
            slug="alcos-operativni-sistem"
            description="Etiam tincidunt mi nisl, at dictum dolor bibendum non. Fusce
              molestie et massa vulputate iaculis. Vestibulum ante ipsum primis
              in faucibus orci luctus et ultrices posuere cubilia curae"
            github-url="https://www.github.com/alcos"
            percent-done="54"
            :tech="['java', 'vuejs', 'html']"
          />
          <ProjectItem
            title="AlcOS"
            slug="alcos-operativni-sistem"
            description="Etiam tincidunt mi nisl, at dictum dolor bibendum non. Fusce
              molestie et massa vulputate iaculis. Vestibulum ante ipsum primis
              in faucibus orci luctus et ultrices posuere cubilia curae"
            github-url="https://www.github.com/alcos"
            percent-done="1"
            :tech="['java', 'vuejs', 'html']"
          />
        </div>
      </div>
      <div class="blog-container subcontainer">
        <div class="subcontainer-title">
          <nuxt-link to="/blog"><h3>writings</h3></nuxt-link>
        </div>
        <div class="subcontainer-content">

          <BlogItem v-for='item in indexData.writings'
                    :category='item.category'
                    :category-slug='item.categorySlug'
                    :description='item.description'
                    :slug='item.slug'
                    :tags='item.tags'
                    :timestamp='item.timestamp'
                    :title='item.title'
                    :key='item.id'/>




        </div>
      </div>
    </div>
    <div class="misc-container subcontainer">
      <div class="subcontainer-title">
        <nuxt-link to="/misc"
          ><h3>misc, hobbies and random stuff</h3></nuxt-link
        >
      </div>
      <div class="subcontainer-content">
        <div class="misc__stuff-list">
          {{ indexData }}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Business',
  props: ['indexData']
}
</script>

<style scoped>
.subcontainer {
  padding: 10px;
  width: 100%;
  /* border: 1px solid teal; */
}

.subcontainer .subcontainer-title {
  border-bottom: 2px solid var(--bg-color-secondary);
}

/*.subcontainer .subcontainer-title a:link {*/
/*  color: #dddddd;*/
/*  text-decoration: none;*/
/*}*/
/*.subcontainer .subcontainer-title a:visited {*/
/*  color: #cccccc;*/
/*}*/
/*.subcontainer .subcontainer-title a:hover,*/
/*.subcontainer .subcontainer-title a:visited:hover {*/
/*  color: #ffffff;*/
/*  !* border-bottom: 1px solid #dddddd; *!*/
/*}*/
/*.subcontainer .subcontainer-title a:active,*/
/*.subcontainer .subcontainer-title a:visited:active {*/
/*  color: #cccccc;*/
/*  border-bottom: none;*/
/*}*/

.subcontainer-content hr {
  border: 1px dashed var(--bg-color-secondary);
  border-radius: 1px;
}

/*@media only screen and (max-width: 400px) {*/
/*  .business {*/
/*    display: flex;*/
/*    width: 100%;*/
/*    !* border: 1px solid blue; *!*/
/*  }*/

/*  .projects {*/
/*    width: 100%;*/
/*    !* border: 1px solid blue; *!*/
/*  }*/

/*  .others-container {*/
/*    width: 100%;*/
/*    !* border: 1px solid blue; *!*/
/*  }*/

/*  .subcontainer-content {*/
/*    width: 100%;*/
/*    padding-top: 20px;*/
/*  }*/

/*}*/

/* Tablet Styles */
@media only screen and (min-width: 401px) and (max-width: 600px) {
  .business {
    padding: 10px;
    display: flex;
    width: 100%;
    /* border: 1px solid blue; */
    flex-wrap: wrap;
  }

  .projects {
    width: 100%;
    /* border: 1px solid blue; */
  }

  .others-container {
    width: 100%;
    /* border: 1px solid blue; */
  }

  .subcontainer-content {
    width: 100%;
    padding-top: 20px;
  }
}

/* Desktop Styles */
@media only screen and (min-width: 600px) {
  .business {
    padding: 10px;
    display: flex;
    width: 100%;
    /* border: 1px solid blue; */
    justify-content: space-between;
  }

  .projects {
    padding-right: 20px;
    /* border: 1px solid blue; */
    margin-right: 20px;
    min-width: 50%;
  }

  .others-container {
    /* border: 1px solid blue; */
  }

  .subcontainer-content {
    width: 100%;
    padding: 20px 10px 10px 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
}
</style>

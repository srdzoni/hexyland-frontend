<template>
    <div class="projects__item">
      <div class="projects__item-avatar">
        <img src="~assets/img/project-placeholder.png" />
      </div>
      <div class="projects__item-header">
        <div class="projects__item-title"><h4>{{ title }}</h4></div>
        <div class="projects__item-percentage"><span :style="{color: percentageStyle2}">{{ percentDone }}%</span></div>
      </div>
      <div class="projects__item-description">
        <p>
          {{ description }}
        </p>
      </div>
      <hr />
      <div class="projects__item-footer">
        <div class="projects_item-footer-github">
          <a :href=githubUrl>
            <font-awesome-icon
              v-bind:style="{color: '#888888', marginRight: 4 + 'px'}"
              :icon="['fab', 'github']"
            />GitHub</a
          >
        </div>
        <div class="projects_item-footer-tech">
          <span class="projects__item-footer-tech-item" v-for='t in tech'>{{ t }}</span>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'ProjectItem',
  props: ["title", "slug", "percentDone", "description", "githubUrl", "tech"],

  computed: {
    percentageStyle2() {
      if(this.percentDone >= 100) return "#00ffff";
      let startR = 86, startG = 44, startB = 58;
      let endR = 0, endG = 255, endB = 0;

      let r = startR + (((endR - startR) * this.percentDone) / 100);
      let g = startG + (((endG - startG) * this.percentDone) / 100);
      let b = startB + (((endB - startB) * this.percentDone) / 100);
      return `rgb(${r}, ${g}, ${b})`;
    }
  }
}
</script>

<style scoped>
.projects__item {
  margin: 0px 10px 10px 0px;
  /* background-color: #30475e; */
  padding: 10px;
  border-radius: 7px;
  -webkit-box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);
}

.projects__item:hover {
  background-color: var(--bg-color-secondary);
}

.projects__item hr {
  border: 1px dashed var(--bg-color-secondary);
  border-radius: 1px;
}

.projects__item:hover hr {
  background-color: var(--bg-color-primary);
}

.projects__item-avatar {
  float: left;
  margin: 0px 15px 0px 5px;
  border-radius: 30%;
  width: 50px;
  height: 50px;
}

.projects__item-avatar img {
  border-radius: 30%;
  width: 50px;
  height: 50px;
}

.projects__item-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.projects__item-title {
}

.projects__item-percentage {
  font-size: small;
  white-space: nowrap;
}

.projects__item-description {
  margin-top: 5px;
  margin-bottom: 10px;
  padding-bottom: 10px;
  color: var(--text-color-secondary);
}

.projects__item-footer {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding-top: 5px;
  clear: both;
  height: 20px;
}

.projects_item-footer-tech {
  display: flex;
  flex-direction: row;
}

.projects__item-footer-tech-item {
  padding-right: 7px;
  color: var(--text-color-tertiary);
  font-size: small;
  font-variation-settings: "slnt" -10;
}

.projects_item-footer-github {
  font-size: smaller;
  display: flex;
}

</style>

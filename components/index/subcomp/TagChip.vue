<template>
<div class='tag-chip'>
  <NuxtLink :to="`/blog/tag/${slug}`">#{{ title }}</NuxtLink>
</div>
</template>

<script>
export default {
  name: 'TagChip',
  props: ["title", "slug"]
}
</script>

<style scoped>

.tag-chip {
  display: inline-block;
  padding: 2px 8px;
  /*height: 50px;*/
  /*font-size: 16px;*/
  /*line-height: 50px;*/
  border-radius: 25px;
  background-color: var(--bg-color-secondary);
}

.tag-chip:hover {
  background-color: var(--bg-color-tertiary);
}

.tag-chip a {
}

</style>

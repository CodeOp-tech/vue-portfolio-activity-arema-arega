<template>

<div :class="{'selected-project': true }">
    <article class="item" v-if="selected">
      <img :src="selected.image" :alt="selected.title" />
      <div class="item__stack">
        <h2 class="item__title">{{ selected.title }}</h2>
        <p class="item__description">{{ selected.description }}</p>
      </div>
    </article>
    <p v-else> Click On any IMAGE to Highlight the Project</p>
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";
export default {
    name: "selectedProject",
    components: {
        ProjectItem,
  },
    props:['selected'],
   
  
}
  

</script>

<style scoped>
.item {
  display: flex;
  flex-direction: column;
  gap: 16px;
  overflow: hidden;
  width: 100%;
}
.item__image {
  aspect-ratio: 1;
  width: 100%;
  object-fit: cover;
  border-radius: 16px;
}
.item__stack {
  display: flex;
  flex-direction: column;
  gap: 8px;
  text-align: center;
}
.item__title {
  margin: 0;
  max-width: 100%;
  overflow: hidden;
  text-overflow: ellipsis;
}
.item__description {
  margin: 0;
}
</style>
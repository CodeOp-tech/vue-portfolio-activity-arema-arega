<template>
  <main>

<div :class="{'selected-project': true }">
    <article class="item__image" v-if="selected">
      <img :src="selected.image" :alt="selected.title" />
      <div class="item__stack">
        <h2 class="item__title">{{ selected.title }}</h2>
        <p class="item__description">{{ selected.description }}</p>
      </div>
    </article>
    <p v-else> Click On any IMAGE to Highlight a Project</p>
  </div>
</main>
</template>

<script>

export default {
    name: "selectedProject",
    
    props:['selected'],
   
  
}
  

</script>

<style scoped>

</style>
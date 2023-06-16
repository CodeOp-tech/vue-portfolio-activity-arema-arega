<template>
<article class="item">
  
  <img
      :class="{'item__image': true}"
      :src="project.image"
      :alt="project.title"
      @click="handleAdd(project)"
    />
   
    <div class="item__stack">
      <h2 class="item__title">{{ project.title }}</h2>
      <p class="item__description">{{ project.description }}</p>
    </div>
  </article>
</template>

<script>
export default {
  name: 'ProjectItem',
  props: ['project'],



  methods: {
    handleAdd(project) {
      this.$emit('add', project); 
      
        
      }
    }
  
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
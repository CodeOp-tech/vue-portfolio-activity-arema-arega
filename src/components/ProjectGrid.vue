<template>
 
  <div v-if="projects.length > 0" class="grid">
    <project-item v-for="project in projects" :key="project.title" :project="project" />
  </div>

  <div class="empty-state" v-else>
    <h2 class="empty-state__title">No Projects</h2>
    <p class="empty-state__description">Add a Project to get started</p>
  </div>
</template>

<script>
import ProjectItem from './ProjectItem.vue';

export default {
  name: 'ProjectGrid',
  props: ['projects'],

  components: {
    ProjectItem,
  },

  data() {
    return {
      selectedProject: null,
    };
  },

  methods: {
    handleSelected(selectedProject) {
      this.selectedProject = selectedProject;
      console.log(selectedProject)
    },
  },
 
}
</script>





<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.empty-state {
  text-align: center;
}

.empty-state__title {
  margin: 0;
  font-size: 28px;
}

.empty-state__description {
  margin: 0;
  font-size: 18px;
}

.grid-item__image {
  aspect-ratio: 1;
  width: 100%;
  object-fit: cover;
  border-radius: 16px;
  box-shadow: 7px 3px 35px 0px rgba(0, 0, 0, 0.2);
}
</style>


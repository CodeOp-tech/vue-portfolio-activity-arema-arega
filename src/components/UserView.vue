<template>
 <div>
    <div :class="{'text_user': true}">User View</div>
   

  
    <div :class="{'selected-project': true }">{{ selectedProject }}</div>
    <SelectedProject :selectedProject= "selectedProject" />
  
    <h1>Portafolio list</h1>

    <div class="container">
      
      <ProjectGrid @add="handleSelected" :projects="projects" />
    </div>
    
  </div>
 
 </template>


<script>
import ProjectGrid from './ProjectGrid.vue';
import SelectedProject from './SelectedProject.vue';

export default {
  name: 'UserView',
  props: ['projects'],
  components: {
    ProjectGrid,
    SelectedProject,
   
  },

  
  
  
};
</script>


<style scoped>
.text_user{
  color: red;
  font-family: 'Gill Sans';

}

.selected-project{
  display: flex;
  flex-direction: column;
  gap: 16px;
  overflow: hidden;
  width: 100%;
}

.main {
  max-width: 1020px;
  width: 100%;
  margin: 0 auto;
}
.container {
  display: flex;
  gap: 16px;
}

.container > * {
  flex: 1;
}
</style>



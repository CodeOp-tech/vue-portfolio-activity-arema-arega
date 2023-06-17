<template>
  <div>
    <div :class="{'text_user': true}">User View</div>
    
    <SelectedProject :selected="selected" />

    <h1>Portafolio list</h1>

    <div class="container">
      <ProjectGrid v-if="projects" :projects="projects" @add2="AddSelected"></ProjectGrid>
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
    SelectedProject,
    ProjectGrid,
   
},

  data() {
    return{
    selected: null,
    }
  },


methods: {
    AddSelected(project) {
    this.selected = project, 
      console.log(this.selected)
    }
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


.container {
  display: flex;
  gap: 16px;
}

.container > * {
  flex: 1;
}
</style>



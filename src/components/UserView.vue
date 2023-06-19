<template>
 <main>
  <div>
    <div :class="{'text_user': true}">User View</div>
    
    <SelectedProject :selected="selected" />

    <h2>PROJECTS list</h2>

    <div class="container">
      <ProjectGrid v-if="projects" :projects="projects" @add2="addSelected"></ProjectGrid>
    </div>
  </div>
 </main>
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
    addSelected(project) {
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



</style>



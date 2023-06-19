<template>
  <main>
  <div>
    <h1>PROJECTS</h1>
    <div :class="container">
    <button :class="{'button':true,'selected-button': isAdmin}" @click="isAdmin = true">ADMIN</button>
    
    <button :class="{'button':true,'selected-button': !isAdmin}" @click="isAdmin = false">USER</button>
    <adminView v-if="isAdmin" @addProject="addProject" />
    <userView v-else :projects="projects" />
  </div>

    
  </div>
 </main> 

</template>

<script>
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";


/*import * as components from "./components";*/

/*
const app = createApp({});
Object.entries(components).forEach(([name, component]) => {
  app.component(name, component);
});


*/


export default {
  name: "app",
  components: {
     UserView,
     AdminView,
    
    
  },
  data() {
    return {
      isAdmin: true,
      projects: [],
      
    };
  },
  methods: {
   addProject(project) {
      this.projects.push(project);
      console.log(project)
    }


  },

};
</script>

<style scoped>

  


.selected-button{
  background-color: rgb(251, 0, 0);
  color:white;

}


</style>

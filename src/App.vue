<template>
  <div>
    <h1>PORTAFOLIOS</h1>
    <button :class="{'button':true,'selected-button': isAdmin}" @click="isAdmin = true">ADMIN</button>
    
    <button :class="{'button':true,'selected-button': !isAdmin}" @click="isAdmin = false">USER</button>
    <adminView v-if="isAdmin" @addProject="addProject" />
    <userView v-else :projects="projects" />
   
    
    
  </div>
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

<style>
div{
  
  align-items: center;
}

h1{
color: rgb(255, 255, 255);
background-image: url("https://i0.wp.com/digital-photography-school.com/wp-content/uploads/2017/08/Alto-Campoo-Ski-Lift-Milky-Way-e1502733284583.jpg?fit=750%2C501&ssl=1")
}




.button{
  
  filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.6));
  padding: 10 100px;
  font-size: 16px;
  height: 42px;
  border-radius: 8px;
  cursor: pointer;
}
.selected-button{
  background-color: rgb(251, 0, 0);
  color:white;

}



</style>

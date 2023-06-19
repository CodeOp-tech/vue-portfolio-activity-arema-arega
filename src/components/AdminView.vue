<template>
  <div class="fondo">
   <form class="form" @submit.prevent="handleSubmit">
    <div class="text-field">
      <label for="project-creation-form-title">TITLE</label>
      <input id="project-creation-form-title" v-model="title" type="text" name="title" />
      <div>{{ title.length }}</div>
    </div>

    <div class="text-field">
      <label for="project-creation-form-description">DESCRIPTION</label>
      <input id="project-creation-form-description" v-model="description" type="text" name="description" />
    </div>

    <div class="text-field">
      <label for="project-creation-form-image">IMAGE</label>
      <input id="project-creation-form-image" v-model="image" type="url" name="image" @input="validateImage" />
      <p class="errorMessage" v-if="errorMessage">{{ errorMessage }}</p>
    </div>

    <div class="button-form-group">
      <button class= "button">SUBMIT</button>
     
    </div>
    </form>
  </div>
   


  
</template>

<script>

export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      description: "",
      image: "",
      errorMessage: '',
    };
  },
  methods: {

    validateImage() {
      const urlRegex = /^(ftp|http|https):\/\/[^ "]+$/;
      if (!urlRegex.test(this.image)) {
       this.errorMessage = 'Invalid URL format';
      } else {
        this.errorMessage = '';  

      }

    },

   

      handleSubmit() {
  if (this.title === "" || this.description === "" || this.image === "") {
    this.errorMessage ='Please fill all the empty fields ';
    return;
  } else {

  this.$emit('addProject', {
    title: this.title,
    description: this.description,
    image: this.image
  });
}
      
      
      
      
      
      this.reset()
    },
    reset() {
      this.title = ''
      this.description = ''
      this.image = ''
      
      
    }
  }
};
</script>


<style scoped>



.button {
  display: flex;
  background-color: #000000;
  color: rgb(255, 255, 255); 
  margin: auto;
}


.button:hover {
  background-color: #ff0000;
}

.button:active {
  background-color: #024eff;
}



</style>

















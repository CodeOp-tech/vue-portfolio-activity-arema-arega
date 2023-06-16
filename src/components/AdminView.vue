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
     
    </div>

    <div class="button-group">
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
      
    };
  },
  methods: {

    validateImage() {
        const urlRegex = /^(ftp|http|https):\/\/[^ "]+$/;
        if (!urlRegex.test(this.image)) {
          console.log('Invalid URL format');
        }
      },

   

    handleSubmit() {
      this.$emit('addProject', {
        title: this.title,
        description: this.description,
        image: this.image
      }
      )
      
      
      this.reset()
    },
    reset() {
      this.title = ''
      this.description = ''
      this.image = ''
      this.isClicked = false;
      
    }
  }
};
</script>


<style scoped>

.fondo{
  background-color: rgb(0, 217, 255);
  border: 200p;
}



.form {
  display: flex;
  flex-direction: column;
  gap: 16px;
  
}

.text-field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.button-group {
  display: flex;
  justify-content: center;
}

.button {
  background-color: #000000;
  color: rgb(255, 255, 255);
  appearance: none;
  border: none;
  padding: 0 16px;
  font-size: 16px;
  height: 42px;
  border-radius: 8px;
  cursor: pointer;
}

.button:hover {
  background-color: #ff0000;
}

.button:active {
  background-color: #024eff;
}



</style>

















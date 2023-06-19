 <template>
 <main>
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
</main> 
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



</style>
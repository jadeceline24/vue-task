<template>
  <header>
    <h1>{{ title }}</h1>
    <Button 
    @btn-click="$emit('toggle-add-task')" 
    :text="showAddTask ? 'Close' : 'Add Task'" 
    :color="showAddTask ? 'red' : 'green'"
    v-show="homePage"/>
  </header>
</template>

<script>
import Button from './Button.vue'
export default {
    name: 'Header ',
    components:{
        Button,
    },
    props: {
    title: String,
    showAddTask: Boolean,
    },
    computed: {
      homePage() {
      if (this.$route.path === '/') {
        return true
      } else {
        return false
      }
    },
  },
    // {title: String}
  
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
<template>
  <div>
  <todo v-bind:todos="todos" @remove-todo="removetodo" @add-todo='addtodo'/>
  </div>
</template>

<script>
import todo from './components/todo.vue'

export default {
  name: 'App',
  components: {
    todo
  },
  data(){
    return{    
      
      
      todos :[
        {
          id:1,
          content:'sample todo 1'
        },
        {
          id:2,
          content:'sample todo 2'
        }
      ]
      }
      

  },
  methods:{
     removetodo(id){
      this.todos= this.todos.filter(todo=>todo.id!=id)
    },
    addtodo(newtodo){
      this.todos=[...this.todos,newtodo]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

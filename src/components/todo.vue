<template>
  <div>
      <h3>Todo List</h3>
      <form >
          <input type="text" v-model="content"  placeholder="Add Todo">
          <button @click="addTodo">submit</button>
      </form>
      
      <div v-bind:key="todo.id" v-for="todo in todos" >
          <todoitem v-bind:todo="todo" @remove-todo="$emit('remove-todo',todo.id)"/>
            <!-- <span>{{todo.content}}</span> -->
      </div>
  </div>
</template>

<script>
import todoitem from './todoitem.vue'
// import uuid from 'uuid'
import { v4 as uuidv4 } from 'uuid';
export default {


name: 'displaytodo',
 components: {
    
    todoitem
  },
props:["todos"],
data(){
    return{
        content:''
    }
},
methods:{
    addTodo(e){
        e.preventDefault();
        if(this.content==''){
            alert('cannot be empty')
        }
        else{
        const newtodo={
            id:uuidv4(),
            content: this.content
        }
        this.$emit('add-todo',newtodo)
        }
       this.content=''
    }
}

}
</script>

<style>

</style>
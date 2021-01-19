<template>
  <div>
      <div>
          <span>{{todo.content}}</span>
          <span><button @click="$emit('remove-todo', todo.id)">delete</button></span>
      </div>
  </div>
</template>

<script>
export default {
props:['todo']

}
</script>

<style>

</style>
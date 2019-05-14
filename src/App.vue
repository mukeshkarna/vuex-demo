<template>
  <div id="app">
    <input v-model="todo" @keyup.enter="saveTodo" type="text" placeholder="Todo Item">
    <ul>
      <li v-for="(todoItem, index) in todos" :key="index">{{todoItem}}</li>
    </ul>
    <TodosCount :count="todos.length"/>
  </div>
</template>

<script>
import TodosCount from './components/TodosCount.vue';

export default {
  name: 'app',
  components: {
    TodosCount
  },
  data:() => ({
    todos: [],
    todo:''
  }),
  methods:{
    saveTodo(){
      this.todos = [
        ...this.todos,
        this.todo
      ]

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input{
  border: 2px solid black;
  padding: 20px;
  font-size: 22px;
}
ul{
  list-style-type: none;
  padding: 0;
}
li{
  font-size: 26px;
}
</style>

<template>
  <div id="app">
    <h1 class="ui dividing centered header">Vue.js Todo App</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
  // Tutorial from : https://scotch.io/tutorials/build-a-to-do-app-with-vue-js-2
  import TodoList from './components/TodoList'
  import CreateTodo from './components/CreateTodo'

  export default {
    name: 'App',
    components: {
      TodoList,
      CreateTodo
    },
    data(){
      return {
        todos: [
          {
            title: 'Todo A',
            project: 'Project A',
            done: false
          },
          {
            title: 'Todo B',
            project: 'Project B',
            done: true
          },
          {
            title: 'Todo C',
            project: 'Project C',
            done: false
          },
          {
            title: 'Todo D',
            project: 'Project D',
            done: true
          }
        ]
      }
    },
    methods: {
      createTodo(newTodo) {
        this.todos.push(newTodo);
        alert('Success! To-Do created!');
      },
    }
  }

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

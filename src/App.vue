<template>
  <div id="app">
    <h1>Todo application</h1>
    <hr>
    <addItem/>
    <todoList
     v-bind:todos="todos"
     @remove-item="removeItem"
     />
  </div>
</template>

<script>
import todoList from '@/components/todoList.vue';
import addItem from '@/components/addItem.vue';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {
          id: 1, title: 'хлеб', completed: false,
        },
        {
          id: 2, title: 'масло', completed: false,
        },
        {
          id: 3, title: 'сыр', completed: false,
        },
      ],
    };
  },
  components: {
    todoList,
    addItem
  },
  methods: {
    removeItem(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    }
  }
};
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

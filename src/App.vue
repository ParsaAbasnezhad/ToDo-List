<template>
  <div class="container">
    <AppHeader />
    <AppToDo @AddNewToDo="AddNewToDo" />
    <div class="todo-empty">
      <ToDo :todos="todos" @DeletToDo="DeletToDoClear" @chengStatus="chengStatus" />
      <AppFooter />
    </div>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppToDo from './components/AppToDo.vue';
import ToDo from './components/ToDo.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppToDo,
    ToDo,
    AppFooter
  },
  data() {
    return {
      todos:
        [

        ]
    }
  },
  methods: {
    AddNewToDo(title) {
      if (title) {
        const id = Math.random().toString(16).slice(2);
        const todo = { id, title: title, isCompleted: false };
        this.todos.push(todo);
      }
    },
    DeletToDoClear(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    }, chengStatus(id, newStatus) {
      this.todos = this.todos.map(todo =>
        todo.id === id ? { ...todo, isCompleted: newStatus } : todo
      );
      console.log(this.todos);
    }
  },
}
</script>

<style>
#app {}
</style>

<template>
  <div class="container">
    <AppHeader />
    <AppToDo @AddNewToDo="AddNewToDo" />
    <div class="todo-empty">
      <ToDo :todos="todos" />
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
        const todo = { title: title, isCompleted: false };
        console.log(todo);
        this.todos.push(todo);
      }
    },
  },
}
</script>

<style>
#app {}
</style>

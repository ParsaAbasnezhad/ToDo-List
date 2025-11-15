<template>
  <div class="container">
    <AppHeader />
    <AppToDo />
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
          { title: 'Buy milk', id: 1, isCompleted: false },
          { title: 'Buy milk1', id: 2, isCompleted: true },
        ]
    }
  },
}
</script>

<style>
#app {}
</style>

<template>
  <div class="container">
    <AppHeader />
    <AppToDo />
    <div class="todo-empty">
      <ToDo />
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

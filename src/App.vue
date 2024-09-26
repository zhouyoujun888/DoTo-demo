<template>
  <div class="app">
    <todo-header></todo-header>
    <todo-main></todo-main>
    <todo-footer></todo-footer>
  </div>
</template>

<script>
import ToDoHeader from './components/ToDoHeader.vue';
import ToDoMain from './components/ToDoMain.vue';
import ToDoFooter from './components/ToDoFooter.vue';
export default {
  name: 'App',
  components: {
    "todo-header": ToDoHeader,
    "todo-main": ToDoMain,
    "todo-footer": ToDoFooter,
  }
}
</script>

<style lang="less">
body {
  margin: 0;
  padding: 0;
  background-color: #f6f6f6;
}

.app {
  margin-top: 100px;
}
</style>

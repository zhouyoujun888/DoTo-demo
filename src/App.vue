<template>
  <div class="app">
    <todo-header @addTodoName="addTodo"></todo-header>
    <todo-main :list="list" @delTodoName="delTodo"></todo-main>
    <todo-footer :list="list" @clear="clearList"></todo-footer>
  </div>
</template>

<script>
import ToDoHeader from './components/ToDoHeader.vue';
import ToDoMain from './components/ToDoMain.vue';
import ToDoFooter from './components/ToDoFooter.vue';
export default {
  name: 'App',
  data() {
    return {
      // list: [{ id: 1, content: "打篮球" }, { id: 2, content: "打羽毛球" }, { id: 3, content: "去游泳" }]
      list: JSON.parse(localStorage.getItem('list')) || []
    }
  },
  components: {
    "todo-header": ToDoHeader,
    "todo-main": ToDoMain,
    "todo-footer": ToDoFooter,
  },
  methods: {
    addTodo(name) {
      this.list.unshift({ id: this.list.length + 1, content: name });
    },
    delTodo(id) {
      this.list = this.list.filter(item => item.id !== id);
    },
    clearList() {
      this.list = [];
    }
  },
  watch: {
    list: {
      deep: true,
      handler() {
        localStorage.setItem('list', JSON.stringify(this.list))
      }
    }
  },
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

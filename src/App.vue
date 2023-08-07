<template>
  <div id="app">
    <h1>TODOLIST--VUE2</h1>
    <TodoInput :onSubmit="onSubmit" />
    <TodoList :list="list" :onDelete="onDelete" />
  </div>
</template>

<script>
import TodoInput from "./components/TodoInput";
import TodoList from "./components/TodoList";

export default {
  name: "App",
  components: {
    TodoInput,
    TodoList,
  },
  data() {
    return {
      list: [],
    };
  },
  methods: {
    onSubmit(value) {
      const nextList = [...this.list];
      nextList.push(value);
      this.list = nextList;
    },
    onDelete(index) {
      const nextList = [...this.list];
      nextList.splice(index, 1);
      this.list = nextList;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

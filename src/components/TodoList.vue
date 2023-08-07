<template>
  <div class="todoList">
    <ol v-if="list.length > 0">
      <li v-for="(item, index) in list" :key="index">
        <span>{{ item }}</span>
        <span @click="handleDelete(index)"
          >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x</span
        >
      </li>
    </ol>
    <div v-else>暂无数据</div>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: { list: Array, onDelete: Function },
  methods: {
    handleDelete(index) {
      this.onDelete(index);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>

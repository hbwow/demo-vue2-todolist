<template>
  <div class="todoInput">
    <input type="text" v-model="value" />
    <button @click="handleSubmit">提交</button>
  </div>
</template>

<script>
export default {
  name: 'TodoInput',
  data() {
    return {
      value: '',
    };
  },
  props: {
    onSubmit: Function,
  },
  methods: {
    handleSubmit() {
      this.onSubmit(this.value);
      this.value = '';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>

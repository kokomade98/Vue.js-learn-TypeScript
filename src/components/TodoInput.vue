<template>
  <div>
    <label for="todo-input">오늘 할 일 : </label>
    <input id="todo-input" type="text" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">추가</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    item: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleInput(event: InputEvent) {
      // 타입 단언
      const eventTarget = event.target as HTMLInputElement;
      this.$emit('input', eventTarget.value);
    },
    addTodo() {
      console.log('add');
      this.$emit('add');
    },
  },
});
</script>

<style scoped></style>

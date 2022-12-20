<script setup lang="ts">
type Todo = { userId: number; id: number; title: string; completed: boolean };
const { data, error } = await useFetch<Todo[]>(() => "https://jsonplaceholder.typicode.com/todos");
</script>
<template>
  <div>
    <div v-if="error">error</div>
    <div v-else-if="!data">loading...</div>
    <div v-else v-for="todo in data" :key="todo.id">
      <p>{{ todo.title }}</p>
    </div>
  </div>
</template>
<style>
.tab-head-wrap {
  display: flex;
  justify-content: space-around;
}
.tab-head-wrap > div {
  background: rgb(240, 238, 238);
  border: 1px solid rgb(146, 140, 140);
  width: 100%;
  height: 40px;
  line-height: 40px;
  text-align: center;
  cursor: pointer;
}
.tab-head-wrap > div:hover {
  opacity: 0.7;
}
</style>

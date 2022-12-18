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

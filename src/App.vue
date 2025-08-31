<template>
  <div class="container py-5">
    <h1 class="fw-bold">To-Do 리스트</h1>
    
    <div class="input-group mb-3">
      <input
        v-model="newTodo"
        type="text"
        class="form-control"
        placeholder="할 일을 입력하세요"
      />
      <button class="btn btn-primary" @click="addTodo">추가</button>
    </div>

    <ul class="list-group">
      <li 
        v-for="todo in todos"
        :key="todo.id"
        class="list-group-item d-flex justify-content-between align-items-center">
          {{ todo.title }}
        <button
          class="btn btn-sm btn-outline-danger"
          @click="removeTodo(todo.id)"
        >
          삭제
        </button>
      </li>
    </ul>
    
  </div>
</template>

<script setup>
import { ref } from 'vue'

const todos = ref([])
const newTodo = ref('')

function addTodo() {
  const text = newTodo.value.trim()
  if (!text) return // 입력이 비어있을 경우, 무시

  todos.value.push({
    id: Date.now(), // 고유 ID (시간 값)
    title: text,
    completed: false // 생성시 완료되지 않은 상태
  })

  newTodo.value = '' // 목록에 추가한 뒤, 입력창을 비움
}

function removeTodo(id) {
  todos.value = todos.value.filter(todo => todo.id !== id)
}
</script>
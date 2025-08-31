<template>
  <div class="container py-5">
    <h1 class="fw-bold">To-Do 리스트</h1>
    
    <div class="input-group mb-3">
      <input
        type="text"
        class="form-control"
        placeholder="할 일을 입력하세요"
      />
      <button class="btn btn-primary">추가</button>
    </div>

    <ul class="list-group">
      <li class="list-group-item d-flex justify-content-between align-items-center">
        예시 할 일 1
        <button class="btn btn-sm btn-outline-danger">삭제</button>
      </li>
      <li class="list-group-item d-flex justify-content-between align-items-center">
        예시 할 일 2
        <button class="btn btn-sm btn-outline-danger">삭제</button>
      </li>
    </ul>
    
  </div>
</template>

<script setup>
</script>
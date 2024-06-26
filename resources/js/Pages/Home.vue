<template>
  <div class="container mx-auto p-4">
    <h1 class="text-4xl font-bold mb-4">렌터카 서비스에 오신 것을 환영합니다</h1>
    <div class="flex space-x-4">
      <Link href="/cars" class="bg-blue-500 text-white px-4 py-2 rounded">차량 목록 보기</Link>
      <Link href="/cars/create" class="bg-green-500 text-white px-4 py-2 rounded">새로운 차량 추가</Link>
    </div>
  </div>
</template>

<script setup>
import { Link } from '@inertiajs/vue3'
</script>

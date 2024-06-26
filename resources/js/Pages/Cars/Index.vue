<template>
  <div class="container mx-auto p-4">
    <h1 class="text-4xl font-bold mb-4">차량 목록</h1>
    <Link href="/cars/create" class="bg-green-500 text-white px-4 py-2 rounded mb-4 inline-block">새로운 차량 추가</Link>
    <ul class="space-y-4">
      <li v-for="car in cars" :key="car.id" class="border p-4 rounded">
        <Link :href="`/cars/${car.id}`" class="text-xl">{{ car.make }} {{ car.model }}</Link>
        <span v-if="car.available" class="ml-4 text-green-500">대여 가능</span>
        <span v-else class="ml-4 text-red-500">대여 불가</span>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
import { Link } from '@inertiajs/vue3'

const props = defineProps({
  cars: Array
})
</script>

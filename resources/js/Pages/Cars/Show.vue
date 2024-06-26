<template>
  <div class="container mx-auto p-4">
    <h1 class="text-4xl font-bold mb-4">{{ car.make }} {{ car.model }}</h1>
    <p class="text-lg">연식: {{ car.year }}</p>
    <p v-if="car.available" class="text-green-500 text-lg">대여 가능</p>
    <p v-else class="text-red-500 text-lg">대여 불가</p>
    <Link :href="`/reservations/create/${car.id}`" class="bg-blue-500 text-white px-4 py-2 rounded mt-4 inline-block" v-if="car.available">이 차량 예약</Link>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
import { Link } from '@inertiajs/vue3'

const props = defineProps({
  car: Object
})
</script>

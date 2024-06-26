<template>
  <div class="container mx-auto p-4">
    <h1 class="text-4xl font-bold mb-4">차량 예약</h1>
    <form @submit.prevent="submit" class="space-y-4">
      <div>
        <label for="start_date" class="block text-lg">예약 시작일</label>
        <Datepicker v-model="form.start_date" class="w-full p-2 border rounded" />
        <div v-if="form.start_date" class="text-green-500">선택한 시작일: {{ form.start_date }}</div>
        <div v-if="form.errors.start_date" class="text-red-500">{{ form.errors.start_date }}</div>
      </div>
      <div>
        <label for="end_date" class="block text-lg">예약 종료일</label>
        <Datepicker v-model="form.end_date" class="w-full p-2 border rounded" />
        <div v-if="form.end_date" class="text-green-500">선택한 종료일: {{ form.end_date }}</div>
        <div v-if="form.errors.end_date" class="text-red-500">{{ form.errors.end_date }}</div>
      </div>
      <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">예약</button>
    </form>
  </div>
</template>

<script setup>
import { useForm } from '@inertiajs/vue3'
import { defineProps } from 'vue'
import Datepicker from 'vue-datepicker-next'
import 'vue-datepicker-next/index.css'

const props = defineProps({
  car: Object
})

const form = useForm({
  start_date: '',
  end_date: ''
})

function submit() {
  form.post(`/reservations/store/${props.car.id}`)
}
</script>

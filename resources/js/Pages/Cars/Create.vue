<template>
  <div class="container mx-auto p-4">
    <h1 class="text-4xl font-bold mb-4">새로운 차량 추가</h1>
    <form @submit.prevent="submit" class="space-y-4">
      <div>
        <label for="make" class="block text-lg">제조사</label>
        <input id="make" v-model="form.make" type="text" class="w-full p-2 border rounded" />
        <div v-if="form.errors.make" class="text-red-500">{{ form.errors.make }}</div>
      </div>
      <div>
        <label for="model" class="block text-lg">모델</label>
        <input id="model" v-model="form.model" type="text" class="w-full p-2 border rounded" />
        <div v-if="form.errors.model" class="text-red-500">{{ form.errors.model }}</div>
      </div>
      <div>
        <label for="year" class="block text-lg">연식</label>
        <input id="year" v-model="form.year" type="number" class="w-full p-2 border rounded" />
        <div v-if="form.errors.year" class="text-red-500">{{ form.errors.year }}</div>
      </div>
      <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">차량 추가</button>
    </form>
  </div>
</template>

<script setup>
import { useForm } from '@inertiajs/vue3'

const form = useForm({
  make: '',
  model: '',
  year: ''
})

function submit() {
  form.post('/cars')
}
</script>

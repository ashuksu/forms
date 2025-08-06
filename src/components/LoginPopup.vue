<script setup>
import {ref} from 'vue'

const show = ref(false)
const email = ref('')
const password = ref('')

function open() {
  show.value = true
}

function close() {
  show.value = false
  email.value = ''
  password.value = ''
}

function submit() {
  alert(`Email: ${email.value}, Password: ${password.value}`)
  close()
}

defineExpose({open, close})
</script>

<template>
  <div v-if="show" class="fixed inset-0 flex items-center justify-center z-50">
    <div
        class="absolute inset-0 bg-stone-750 backdrop-blur-lg"
        @click="close"
    >
    </div>

    <div
        class="relative bg-white text-gray-900 rounded-lg shadow-md border border-gray-200 p-6 w-full max-w-md z-10"
        @click.stop
    >
      <h2 class="text-xl font-semibold mb-4">Login</h2>
      <form
          @submit.prevent="submit">
        <div class="mb-4">
          <label for="email" class="block mb-1">Email</label>
          <input
              id="email"
              type="email"
              placeholder="Enter your email"
              v-model="email"
              class="w-full border border-gray-300 rounded-lg px-3 py-2 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-gray-400"
              required
          />
        </div>
        <div class="mb-6">
          <label for="password" class="block mb-1">Password</label>
          <input
              id="password"
              type="password"
              placeholder="Enter your password"
              v-model="password"
              class="w-full border border-gray-300 rounded-lg px-3 py-2 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-gray-400"
              required
          />
        </div>
        <button
            type="submit"
            class="bg-gray-800 text-white px-4 py-2 rounded-lg hover:bg-gray-700 transition"
        >
          Login
        </button>
        <button
            type="button"
            @click="close"
            class="ml-4 px-4 py-2 rounded-lg border border-gray-400 hover:bg-gray-100 transition"
        >
          Cancel
        </button>
      </form>
    </div>
  </div>
</template>
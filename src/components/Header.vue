<script setup>
import {ref} from 'vue'

const loginPopup = ref(null)

function openLogin() {
  loginPopup.value.open()
}
</script>

<template>
  <header class="bg-gray-800 text-white py-4">
    <div class="container-box flex items-center justify-center">
      <nav class="flex items-center space-x-4">
        <a href="#" @click.prevent="$emit('open-login')" class="nav-link">Login</a>
        <a href="#registration" class="nav-link">Registration</a>
        <a href="#feedback" class="nav-link">Feedback</a>
      </nav>
    </div>
  </header>

  <LoginPopup ref="loginPopup" />
</template>
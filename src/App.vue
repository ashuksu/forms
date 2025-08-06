<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <Header/>

    <main class="flex-1">
      <section class="container-box py-8">
        <h1 class="text-2xl font-bold mb-4 text-center">Home page</h1>
        <p class="text-center">This is the main content area.</p>
      </section>
    </main>

    <Footer/>
  </div>
</template>
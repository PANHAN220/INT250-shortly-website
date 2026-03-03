<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
</script>

<template>
 
<nav class="flex items-center justify-between px-8 py-4">
    <div class="flex items-center gap-10">
        <!-- Logo -->
        <h1 class="text-2xl font-bold">Shortly</h1>

        <!-- Desktop Menu -->
        <div class="hidden lg:flex gap-6 font-bold">
        <a href="#">Features</a>
        <a href="#">Pricing</a>
        <a href="#">Resources</a>
        </div>
    </div>

    <div class="hidden lg:flex gap-4 items-center">
      <a href="#">Login</a>
      <button class="bg-cyan-500 text-white px-4 py-2 rounded-full">
        Sign Up
      </button>
    </div>

    <!-- Hamburger -->
    <button 
      class="lg:hidden"
      @click="isOpen = !isOpen">
      ☰
    </button>
  </nav>

  <!-- Mobile Menu -->
  <div v-if="isOpen" class="lg:hidden bg-slate-800 text-white p-6 space-y-4 text-center">
    <a href="#">Features</a>
    <a href="#">Pricing</a>
    <a href="#">Resources</a>
    <hr>
    <a href="#">Login</a>
    <button class="bg-cyan-500 w-full py-2 rounded-full">
      Sign Up
    </button>
  </div>
</template>
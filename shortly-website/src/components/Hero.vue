<script setup>
import heroImage from '../assets/undraw_link-shortener_9ro5.svg'
</script>

<template>
  <section class="flex flex-col-reverse lg:flex-row items-center p-8 gap-10">
    
    <!-- Text -->
    <div class="text-center lg:text-left flex-1">
      <h2 class="text-4xl font-bold mb-4">
        Turn every link into a brand touchpoint
      </h2>
      <p class="text-gray-500 mb-6">
        Boost trust with branded links—and see exactly how every link performs.
      </p>
      <button class="bg-cyan-500 text-white px-6 py-3 rounded-full">
        Get Started
      </button>
    </div>

    <!-- Image -->
    <div class="flex-1">
      <img :src="heroImage" alt="hero">
    </div>

  </section>
</template>
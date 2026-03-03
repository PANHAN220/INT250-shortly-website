<script setup>
import bgDesktop from '../assets/bg-boost-desktop.svg'
import bgMobile from '../assets/bg-boost-mobile.svg'
</script>

<template>
  <section
    class="text-center text-white py-16 bg-indigo-900 bg-no-repeat bg-cover"
    :style="{ backgroundImage: `url(${bgDesktop})` }"
  >
    <h2 class="text-3xl font-bold mb-6">
      Boost your links today
    </h2>

    <button class="bg-cyan-500 px-6 py-3 rounded-full">
      Get Started
    </button>
  </section>
</template>
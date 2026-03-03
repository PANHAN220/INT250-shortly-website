<script setup>
import { ref } from 'vue'

const link = ref('')
const error = ref('')
const links = ref([])

function shorten() {
  if (!link.value) {
    error.value = 'Please add a link'
    return
  }

  error.value = ''
  links.value.push({
    original: link.value,
    short: 'https://rel.ink/' + Math.random().toString(36).slice(2,7)
  })
  link.value = ''
}

function copyText(text) {
  navigator.clipboard.writeText(text)
}
</script>

<template>
  <section class="p-8 bg-gray-100">
    
    <!-- Form -->
    <div class="bg-indigo-900 p-6 rounded-lg flex flex-col md:flex-row gap-4">
      <input
        v-model="link"
        placeholder="Shorten a link here"
        class="flex-1 p-3 rounded bg-white"
      >
      <button
        @click="shorten"
        class="bg-cyan-500 text-white px-6 py-3 rounded">
        Shorten It!
      </button>
    </div>

    <p v-if="error" class="text-red-500 mt-2">{{ error }}</p>

    <!-- Link Cards -->
    <div class="mt-6 space-y-4">
      <div 
        v-for="(item, index) in links"
        :key="index"
        class="bg-white p-4 rounded flex flex-col md:flex-row md:items-center md:justify-between gap-4"
      >
        <p>{{ item.original }}</p>
        <div class="flex flex-col md:flex-row md:items-center gap-4">
          <p class="text-cyan-500">{{ item.short }}</p>
          <button
            @click="copyText(item.short)"
            class="bg-cyan-500 text-white px-4 py-2 rounded">
            Copy
          </button>
        </div>
      </div>
    </div>

  </section>
</template>
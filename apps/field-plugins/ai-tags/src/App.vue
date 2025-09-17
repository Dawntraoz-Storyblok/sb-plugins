<script setup lang="ts">
import { ref } from 'vue'
import FieldPlugin from './components/FieldPlugin.vue'
import FieldPluginExample from './components/FieldPluginExample/index.vue'

const isDemoMode = ref(true)
</script>

<template>
  <FieldPluginExample v-if="isDemoMode" />
  <FieldPlugin v-else />
  <hr />
  <button
    class="btn w-full"
    @click="isDemoMode = !isDemoMode"
  >
    Toggle Demo Mode
  </button>
</template>

<script setup lang="ts">
import type { SetModalOpen } from '@storyblok/field-plugin'

const props = defineProps<{
  isModalOpen: boolean
  setModalOpen: SetModalOpen<number>
}>()
</script>

<template>
  <div>
    <h2># Demo 6 - Advance interactions: Modal</h2>
    <button
      class="btn w-full"
      type="button"
      @click="() => props.setModalOpen(!props.isModalOpen)"
    >
      {{ props.isModalOpen ? 'Close' : 'Open' }} modal
    </button>
  </div>
</template>

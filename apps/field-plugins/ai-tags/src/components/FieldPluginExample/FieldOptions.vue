<script setup lang="ts">
const props = defineProps<{ options: Record<string, string> }>()
</script>

<template>
  <div>
    <h2># Demo 5 - Options: Brand sample</h2>
    <p>
      {{ props.options }}
    </p>
  </div>
</template>

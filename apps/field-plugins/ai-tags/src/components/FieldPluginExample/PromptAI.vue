<script setup lang="ts">
import { ref } from 'vue'
import type { PromptAI } from '@storyblok/field-plugin'

const props = defineProps<{
  isAIEnabled: boolean
  promptAI: PromptAI
}>()

const aiResponse = ref<string>('')

const actionPromptAI = async () => {
  if (!props.isAIEnabled) return
  const response = await props.promptAI({
    action: 'prompt',
    text: 'Generate a list of tags for a blog post',
    basedOnCurrentStory: true,
  })

  if (response.ok) aiResponse.value = response.answer
}
</script>

<template>
  <div>
    <h2># Demo 6 - Advance interactions: Prompt AI</h2>
    <p v-if="aiResponse">AI response: {{ aiResponse }}</p>
    <button
      class="btn w-full"
      type="button"
      :disabled="!props.isAIEnabled"
      @click="actionPromptAI"
    >
      {{ props.isAIEnabled ? 'Use AI to generate tags' : 'AI is disabled' }}
    </button>
  </div>
</template>

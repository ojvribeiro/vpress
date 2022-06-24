<template>
  <article class="post">
    <h1 class="text-4xl text-blue-400">
      {{ props.title }}
    </h1>

    <div v-html="props.body"></div>
  </article>
</template>


<script setup>
  const props = defineProps({
    id: {
      type: Number,
    },
    title: {
      type: String,
      default: '',
    },
    body: {
      type: String,
      default: '',
    },
  })
</script>

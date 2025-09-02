<script setup>

const props = defineProps({
  details: {
    type: String,
    required: true
  }
})

</script>

<template>
  <p>{{ props.details }}</p>
</template>
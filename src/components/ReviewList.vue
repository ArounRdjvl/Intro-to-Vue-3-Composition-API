<script setup>
defineProps({
  reviews: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="review-container">
    <h3>Reviews:</h3>
    <ul>
      <li v-for="(review, index) in reviews" :key="index">
        <span>{{ review.name }} gave this {{ review.rating }} stars</span>
        <span>{{review.recommended? " and recommended this product":""}}</span>
        <br/>
        <span>"{{ review.content }}"</span>
      </li>
    </ul>
  </div>
</template>
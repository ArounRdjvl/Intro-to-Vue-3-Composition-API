<script setup lang="ts">

interface Review {
  name: string,
  content: string,
  rating: number,
  recommended:boolean
}

interface Props {
  reviews: Array<Review>
}
const props = defineProps<Props>();


</script>

<template>
  <div class="review-container">
    <h3>Reviews:</h3>
    <ul>
      <li v-for="(review, index) in props.reviews" :key="index">
        <span>{{ review.name }} gave this {{ review.rating }} stars</span>
        <span>{{review.recommended? " and recommended this product":""}}</span>
        <br/>
        <span>"{{ review.content }}"</span>
      </li>
    </ul>
  </div>
</template>

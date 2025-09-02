<script setup>
import { reactive } from 'vue'

const emit = defineEmits(['review-submitted'])

const review = reactive({
  name: '',
  content: '',
  rating: null,
  recommended:false
})

const onSubmit = () => {
  if (review.name === '' || review.content === '' || review.rating === null || review.recommended === null) {
    alert('Review is incomplete. Please fill out every field.')
    return
  }

  const productReview = {
    name: review.name,
    content: review.content,
    rating: review.rating,
    recommended: review.recommended
  }
  emit('review-submitted', productReview)

  review.name = ''
  review.content = ''
  review.rating = null
  review.recommended = false
}
</script>

<template>
  <form class="review-form" @submit.prevent="onSubmit">
    <h3>Leave a review</h3>
    <label for="name">Name:</label>
    <input id="name" v-model="review.name">

    <label for="review">Review:</label>      
    <textarea id="review" v-model="review.content"></textarea>

    <label for="rating">Rating:</label>
    <select id="rating" v-model.number="review.rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>

    <label for="recommended">Would you recommend this product?</label>
    <input type="checkbox" id="recommended" value="true" v-model="review.recommended"/>
    
    <input class="button" type="submit" value="Submit">
  </form>
</template>
<template>
  <div class="star-icon">
    <StarIcon :fill="fill" />
  </div>
</template>

<script>
import StarIcon from './star-icon.vue'

export default {
  name: 'RatingIcon',
  components: {
    StarIcon,
  },
  props: {
    index: Number,
    rating: Number,
    hoverRating: Number,
  },
  computed: {
    fill: function() {
      if (
        this.hoverRating >= this.index ||
        (!this.hoverRating && this.rating >= this.index)
      ) {
        return 'yellow'
      }
      return 'none'
    },
  },
}
</script>

<style scoped>
.star-icon {
  cursor: pointer;
  display: block;
}
</style>

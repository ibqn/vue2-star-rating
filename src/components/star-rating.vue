<template>
  <div class="star-rating">
    <RatingIcon
      v-for="index in stars"
      :key="index"
      :index="index"
      :rating="rating"
      :hoverRating="hoverRating"
      @mouseenter.native="mouseEnter(index)"
      @mouseleave.native="mouseLeave()"
      @click.native="saveRating(index)"
    />
  </div>
</template>

<script>
import RatingIcon from './rating-icon.vue'

export default {
  name: 'StarRating',
  components: {
    RatingIcon,
  },
  data() {
    return {
      hoverRating: 0,
      rating: 0,
    }
  },
  props: {
    stars: Number,
  },
  methods: {
    saveRating: function(index) {
      this.rating = index
    },
    mouseEnter: function(index) {
      this.hoverRating = index
    },
    mouseLeave: function() {
      this.hoverRating = 0
    },
  },
}
</script>

<style scoped>
.star-rating {
  display: flex;
  width: 300px;
}
</style>

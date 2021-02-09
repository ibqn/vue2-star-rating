<template>
  <div class="app">
    <p>Hello world</p>

    <div v-if="counter > 0">you have {{ counter }} 👍 like(s)!</div>
    <button @click="increment">👍 like</button>
    <div class="rating-box">
      Star rating
      <StarRating :stars="5" />
    </div>
  </div>
</template>

<script>
import StarRating from './components/star-rating.vue'

export default {
  name: 'App',
  components: {
    StarRating,
  },
  data: function() {
    return {
      counter: 0,
    }
  },
  methods: {
    increment: function() {
      this.counter++
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  height: 100vh;
  margin: 0;
  display: grid;
  place-items: center;
}

button {
  margin-bottom: 1.25rem;
}

.rating-box {
  background-color: #fff;
  border-radius: 6px;
  box-shadow: 0 2px 3px rgb(10 10 10 / 10%), 0 0 0 1px rgb(10 10 10 / 10%);
  color: #4a4a4a;
  padding: 1.25rem;
}
</style>

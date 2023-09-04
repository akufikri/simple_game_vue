<template>
  <div class="row mb-5 mt-5">
    <div class="col justify-content-center text-center align-items-center">
      <h1>Simple Game With Vue Js</h1>
      <div class="mt-5">
        <button class="btn btn-danger btn-lg" @click="start">Click Me</button>
      </div>
    </div>
  </div>
  <div class="row justify-content-center">
    <div class="col-md-5">
      <Block v-if="isPlaying" :disabled="isPlaying" :delay="delay" @end="endGame" />
      <Resault v-if="showResault" :score="score" />
    </div>
  </div>
</template>

<script>
import Block from './Components/Block.vue';
import Resault from './Components/Resault.vue';
export default {
  name: "App",
  components: {
    Block,
    Resault
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResault: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true;
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResault = true
    }
  }
}
</script>

<style></style>
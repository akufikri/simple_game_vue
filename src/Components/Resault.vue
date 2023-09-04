<template>
      <div class="text-center">Reactions Time: - {{ score }} ms</div>
      <h5 class="text-center fw-bold">Your Rank {{ rank }}</h5>
</template>

<script>
export default {
      props: ['score'],
      data() {
            return {
                  rank: null
            }
      },
      mounted() {
            if (this.score < 250) {
                  this.rank = 'Ninja Fingers'
            } else if (this.score > 400) {
                  this.rank = 'Rapid Refleks'
            } else {
                  this.rank = 'Snail Place...'
            }
      }
}
</script>

<style></style>
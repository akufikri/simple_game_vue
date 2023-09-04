<template>
      <div class="card bg-success text-white border-0 shadow p-5 rounded-4" v-if="showBlocks" @click="stopTimer">
            <div class="card-body">
                  <h4 class="text-center">Click Me</h4>
            </div>
      </div>
</template>

<script>
export default {
      props: ['delay'],
      data() {
            return {
                  showBlocks: false,
                  timer: null,
                  reactionTime: 0
            }
      },
      mounted() {
            console.log('Component Mounted')
            setTimeout(() => {
                  this.showBlocks = true,
                        this.startTimer()
            }, this.delay)
      },
      methods: {
            startTimer() {
                  this.timer = setInterval(() => {
                        this.reactionTime += 10
                  }, 10)
            },
            stopTimer() {
                  clearInterval(this.timer)
                  this.$emit('end', this.reactionTime)
            }
      }
}
</script>

<style></style>
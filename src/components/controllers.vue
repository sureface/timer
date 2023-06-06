<template>
  <div class="flex items-center justify-center mb-10">
    <button type="button" class="py-3 px-5 text-white bg-blue-500 rounded-lg mr-3 text-lg font-semibold capitalize" @click="$emit('reset', $event)">reset</button>
    <button type="button" class="py-3 px-5 text-white bg-blue-500 rounded-lg text-lg font-semibold capitalize" @click="start">{{ play ? 'pause' : 'start' }}</button>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "controllers",
  data() {
    return {
      play: false
    }
  },
  props: {
    timeAdded: Boolean,
  },
  methods: {
    start() {
      this.play = !this.play
      this.$emit('play', event)
    }
  },
  watch: {
    timeAdded: function (val) {
      if (val === true) {
        this.play = !this.play
      }
    }
  }
}
</script>

<style scoped>

</style>
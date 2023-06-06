<template>
  <div class="flex items-center justify-center">
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 60)"
    >
      +1m
    </div>
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 300)"
    >
      +5m
    </div>
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 600)"
    >
      +10m
    </div>
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 900)"
    >
      +15m
    </div>
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 1800)"
    >
      +30
    </div>
    <div class="w-16 h-16 mr-4 cursor-pointer rounded-full bg-blue-500 font-semibold hover:shadow-lg transition-shadow text-lg text-white flex items-center justify-center"
      @click="$emit('addTime', 3600)"
    >
      +1h
    </div>
  </div>
</template>

<script>
export default {
  name: "updateTime",
  data() {
    return {

    }
  }
}
</script>

<style scoped>

</style>
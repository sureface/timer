<template>
  <div id="app">
      <div class="flex items-center justify-center flex-col w-screen h-screen">

        <update-time
          @addTime="updateTime"
        />

        <div class="flex items-center font-bold text-gray-600 text-size">
          {{ hours + ':' + minutes + ':' + seconds + '.'}}
          <div class="w-56 flex items-center">
            <div>{{ milliseconds }}</div>
            <div class="text-7xl">ms</div>
          </div>
        </div>

        <controllers
            @play="toggler"
            @reset="reset"
            :timeAdded="isPlay"
        />

      </div>
  </div>
</template>

<script>

import Controllers from "@/components/controllers";
import UpdateTime from "@/components/updateTime";
export default {
  name: 'App',
  components: {UpdateTime, Controllers},
  data(){
    return{
      timer: null,
      default_min: 60 * 1000,
      hours:0,
      minutes:0,
      seconds:0,
      milliseconds:0,
      isPlay: false,
    }
  },
  methods:{
    updateTime(time) {
      this.isPlay = true
      this.default_min =  (this.default_min / 1000 + time) * 1000
      this.play()
    },
    reset() {
      this.pause()
      this.isPlay = false
      this.timer = null
      this.default_min = 10 * 1000
      this.hours = 0
      this.minutes = 0
      this.seconds = 0
      this.milliseconds = 0
      clearInterval(this.timer)
    },
    pause(){
      clearInterval(this.timer);
    },
    toggler() {
      this.isPlay = !this.isPlay

      if (this.isPlay === true) {
        this.play()
      } else this.pause()
    },
    play(){
      clearInterval(this.timer);
      let countDownDate = this.default_min;
      this.timer = setInterval(()=> {
        for(let i = 0; i < 10; i++) {
          countDownDate--
        }
        this.hours = Math.floor((countDownDate % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        this.minutes = Math.floor((countDownDate % (1000 * 60 * 60)) / (1000 * 60));
        this.seconds = Math.floor((countDownDate % (1000 * 60)) / 1000);
        this.milliseconds = Math.floor((countDownDate % 1000));

        if (countDownDate == 0) {
          clearInterval(this.timer);
        }
      }, 10);
    },
  },
}
</script>

<style>

</style>

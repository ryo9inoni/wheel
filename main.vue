<template lang="pug">
.contents(@wheel="Wheel")
</template>

<script>
export default {
  data(){
    return{
      sliderLastTime: 0,
      sliderLockTime: 1300,
    }
  },
  methods:{
    Wheel(e){
      // イベントが発火してからthis.sliderLockTime秒以上経つまで発火させない
      const timeNow = new Date().getTime()
      if(timeNow - this.sliderLastTime < this.sliderLockTime) return

      this.sliderLastTime = timeNow
    },
  }
}
</script>
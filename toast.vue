<style scoped lang="stylus">
.toast
  position fixed
  top 50%
  left 50%
  z-index 999
  transform translate(-50%, -50%)
  box-sizing border-box
  box-shadow 0 16px 32px 0 rgba(0, 0, 0, 0.2)
  padding 1.2rem 1.6rem
  font-family SFProDisplay-Regular
  font-size 1.5rem
  color #FFFFFF
  text-align center
  letter-spacing 0
  background rgba(0, 0, 0, 0.72)
  border-radius 0.4rem
</style>
<template lang="pug">
  .toast(v-if="showToast")
    .msg {{ msg }}
</template>
<script>
export default {
  props: {
    msg: {
      required: true
    },
    time: {
      default: 1000
    }
  },
  data() {
    return {
      showToast: false
    }
  },
  methods: {
    show() {
      this.showToast = true
      setTimeout(() => {
        this.showToast = false
      }, this.time)
    }
  }
}
</script>

<style scoped lang="stylus">
.shadow {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 99;
  background: rgba(0,0,0,0.72);
  .modal {
    position: fixed;
    top: 50%;
    left: 50%;
    width: 28.8rem;
    height: 14.2rem;
    overflow: hidden;
    font-size: 1.6rem;
    transform: translate(-50%,-50%);
    background: #ffffff;
    border-radius: 0.4rem;
    .modalTitle {
      height: 9.4rem;
      line-height: 9.4rem;
      text-align: center;
      border-bottom: 0.05rem solid #EBEBEB;
    }
    .modalOperate {
      display: flex;
      height: 4.8rem;
      .cancel,.confirm {
        flex: 1 1 auto;
        line-height: 4.8rem;
        text-align: center;
      }
      .confirm {
        color: #24C789;
      }
      .cancel {
        color: #333333;
        border-right: 0.05rem solid #EBEBEB;
      }
    }
  }
}
</style>
<template lang="pug">
  .shadow(v-if="showModal",@click.stop="")
    .modal
      .modalTitle {{title}}
      .modalOperate
        .cancel(@click.stop="cancel") {{cancelText}}
        .confirm(@click.stop="confirm") {{confirmText}}
</template>
<script>
export default {
  props: ['title', 'confirmText', 'cancelText', 'showModal'],
  methods: {
    cancel() {
      this.$emit('cancel')
    },
    confirm() {
      this.$emit('confirm')
    }
  }
}
</script>

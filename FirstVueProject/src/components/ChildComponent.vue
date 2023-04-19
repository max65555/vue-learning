<template>
  <div>
    <p class="">hello</p>
    <img :class="$attrs.class" src="https://img.olympicchannel.com/images/image/private/t_s_w960/t_s_16_9_g_auto/f_auto/primary/tdslyl0pptzs6vst4uq5" alt="">
  </div>
</template>

<script>
  export default {
    name:"ChildComponent"
  }
</script>

<style lang="scss" scoped>
div{
  .image-pic{
    width:120px;
    height:120px;
  }
}
</style>
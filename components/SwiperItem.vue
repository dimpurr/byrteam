<template>
    <div class="swiper-item" :class="{hidden:!show,visible:!!show}">
        <slot></slot>
    </div>
</template>
<script>
export default {
    props:['show']
}
</script>
<style lang="sass" scoped>
.swiper-item
    position: absolute
    left: 0
    top: 0
    right: 0
    bottom: 0
.visible 
  visibility: visible
  opacity: 1
  transition: opacity 0.5s linear

.hidden 
  visibility: hidden
  opacity: 0
  transition: visibility 0s 0.5s, opacity 0.5s linear


</style>

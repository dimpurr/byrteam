<template>
    <span class="btn" :class="{flat,outline,large}"><slot /></span>
</template>
<script>
export default {
    props:['flat','outline','large']
}
</script>
<style lang="sass" scoped>
.btn
    cursor: pointer
    font-size: 1rem
    padding: 1.3rem 2.1rem
    display: flex
    width: 6rem
    justify-content: center
    align-items: center
    background: rgb(102, 204, 255)
    color: white
.flat
    background: none !important
    color: rgb(127, 127, 127)

.outline
  border-width: 1px
  border-color: rgb(102, 204, 255)
  border-style: solid
  border-radius: 1rem
  background: none
  color: rgb(177, 177, 177)
  padding: 0.6rem

.large
    width: 6rem
    height: 3rem
</style>

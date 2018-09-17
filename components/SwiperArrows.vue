<template>

            <div class="arrows">

                <span :class="{visible:!isFirst,hidden:!!isFirst}" @click="$emit('prev')">&lt;</span>
                <span :class="{visible:!isLast,hidden:!!isLast}" @click="$emit('next')">&gt;</span>
            </div>
</template>
<script>
export default {
    props:['isFirst','isLast']

}
</script>
<style lang="sass" scoped>
.arrows *
    font-weight: 100
    cursor: pointer
    font-size: 1.6rem
    color: rgb(125, 125, 125)
    padding: 0.2rem

.visible 
  visibility: visible
  opacity: 1
  transition: opacity 0.2s linear

.hidden 
  visibility: hidden
  opacity: 0
  transition: visibility 0s 0.2s, opacity 0.2s linear
</style>

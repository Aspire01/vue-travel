<template>
    <div class="weekend-wrapper">
        <div class="slicer"></div>
        <div class="w-title-wrap">
            <div>1</div>
            <div>2</div>
        </div>
    </div>
</template>

<script>
export default {
    name:'HomeWeekend'
}
</script>

<style lang="stylus" scoped>
    .weekend-wrapper
        background #fff
       .slicer
         height .2rem
         background #f5f5f5
       .w-title-wrap
            display flex
            padding .24rem .48rem .26rem
            justify-content space-between
            align-items center
</style>
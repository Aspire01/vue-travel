<template>
    <div class="icons">
        Icons
    </div>
</template>

<script>
export default {
    name:'HomeIcons',
}
</script>

<style lang="stylus" scoped>
    // 实现宽高比2:1的盒子 这是什么原理？
    .icons
        height 0
        overflow hidden
        padding-bottom 50%
        background pink    
</style>
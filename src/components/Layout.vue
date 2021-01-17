<template>
    <div class="vue-wraper">
        <div class="content" :class="classPrefix && `${classPrefix}-content`">
            <slot/>
        </div>
        <Nav/>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue'

    export default Vue.extend({
        props:['classPrefix']
    })
</script>

<style lang="scss" scoped>
    .vue-wraper {
        display: flex;
        flex-direction: column;
        height:100vh;
    }
    .content {
        flex: 1;
        overflow:auto;
    }
</style>
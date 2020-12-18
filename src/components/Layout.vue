<template>
    <div class="vue-wraper">
        <div class="content">
            <slot/>
        </div>
        <Nav/>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue'

    export default Vue.extend({
        
    })
</script>

<style lang="scss" scoped>
    .vue-wraper {
        border:1px solid red;
        display: flex;
        flex-direction: column;
        height:100vh;
    }
    .content {
        flex: 1;
        overflow:auto;
    }
</style>
<template>
    <div>
        <router-link to="/money">
        <svg>
            <use xlink:href="#money"/>
        </svg>
        记账
        </router-link>
    |
    <router-link to="/labels">
    <svg>
        <use xlink:href="#labels"/>
    </svg>
    标签
    </router-link>
    |
    <router-link to="/stat">
    <svg>
        <use xlink:href="#statistics"/>
    </svg>
    统计
    </router-link>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue'
    const importAll = (requireContext: __WebpackModuleApi.RequireContext) => requireContext.keys().forEach(requireContext);
    try {
        importAll(require.context('../assets/icons',true,/\.svg$/));
    } catch (error) {
        console.log(error)
    }
    
    export default Vue.extend({
        
    })
</script>

<style scoped>

</style>
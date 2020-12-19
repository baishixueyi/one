<template>
  <nav>
    <router-link to="/money" class="item" active-class="select"> <Icon name="money"/>记账 </router-link>
    <router-link to="/labels" class="item" active-class="select"> <Icon name="labels"/>标签 </router-link>
    <router-link to="/stat" class="item" active-class="select"> <Icon name="statistics"/>统计 </router-link>
  </nav>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>
<style lang="scss" scoped>
    nav{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 56px;
        border-top: 1px solid #999999;
        font-size: 12px;
        color:#999999;
        > .item {
            flex:1;
            display:flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding:3px 0;
            .icon {
                height:27px;
                width:27px;
            }
        }
        > .item.select {
            color:red;
        }
    }
</style>
<template>
  <div>
    <router-link to="/money">
      <Icon name="money" />
      记账
    </router-link>
    |
    <router-link to="/labels"> <Icon name="labels" />标签 </router-link>
    |
    <router-link to="/stat">
      <Icon name="statistics" />
      统计
    </router-link>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  
});
</script>

<style scoped>
</style>
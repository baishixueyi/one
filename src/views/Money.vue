<template>
  <Layout class-prefix="layout">
    <Labels />
    <Notes />
    <NumberPad/>
  </Layout>
</template>

<script lang="ts">
import Vue from "vue";
import Labels from "@/components/Money/Labels.vue";
import Notes from "@/components/Money/Notes.vue";
import NumberPad from "@/components/Money/NumberPad.vue";
export default Vue.extend({
  components: { Labels,Notes,NumberPad },});
</script>
<style lang="scss">
  .layout-content {
    display: flex;
    flex-direction: column;
  }
</style>
<style lang="scss" scoped>
</style>
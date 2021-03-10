<template>
  <Layout class-prefix="layout">
    <Labels :data-soruce.sync = "labelData"/>
    <Notes/>
    <NumberPad/>
  </Layout>
</template>

<script>
import Vue from "vue";
import Labels from "@/components/Money/Labels.vue";
import Notes from "@/components/Money/Notes.vue";
import NumberPad from "@/components/Money/NumberPad.vue";
export default{
  name:'Money',
  components: { Labels,Notes,NumberPad },
  data(){
    return {
      labelData:['衣','食','住','行']
    }
  }
  };
</script>
<style lang="scss">
  .layout-content {
    display: flex;
    flex-direction: column;
  }
</style>
<style lang="scss" scoped>  
</style>
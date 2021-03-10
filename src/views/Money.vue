<template>

  <Layout class-prefix="layout">
    <Labels :data-soruce.sync = "labelData" @update:value="onChangeLabels"/>
    <Notes @update:value = "onChangeNotes"/>
    <NumberPad @update:value = "onChangeNumber" :type.sync="record.type"/>
    {{record}}
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
        labelData:['衣','食','住','行'],
        record:{tags:[],note:'',type:'-',number:0}
      }
    },
    methods:{
      onChangeLabels(value){
        this.record.tags = value
        console.log(value)
      },
      onChangeNotes(value){
        this.record.note = value
        console.log(value)
      },
      onChangeNumber(value){
        this.record.type = value[0]
        this.record.number = value[1]
        console.log(value)
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
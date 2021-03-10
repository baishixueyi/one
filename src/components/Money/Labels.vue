import { Component } from 'vue-property-decorator';
<template>
    <div class="top">
      <ul class="labals">
        <li :class="{selected:selectLables.indexOf(val)>=0} " v-for="val in dataSoruce" :key="val" @click="selectLabel">{{val}}</li>
      </ul>
      <button class="newlabals" @click="addLabels">新增标签</button>
    </div>
</template>

<script>
  import {Component,Prop,Vue} from 'vue-property-decorator';
  @Component
  export default class Labels extends Vue {
    @Prop() dataSoruce
    selectLables = []
    selectLabel(e){
      const selectVal = e.target.innerText;
      const index = this.selectLables.indexOf(selectVal)
      if(index>=0){
        this.selectLables.splice(index,1)
      }else {
        this.selectLables.push(selectVal)
      }
    }
    addLabels(){
      const name = window.prompt('请输入标签');
      if(name!=''){
        this.$emit('update:dataSoruce',[...this.dataSoruce,name]);
      }else {
        window.alert('标签名不能为空');
      }
      
      console.log(name)
    }
  }
</script>

<style lang="scss" scoped>
.top {
  padding: 12px 16px;
  background: #ffffff;
  > .labals {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: flex-end;
    height: 95px;
    overflow: scroll;
    > li {
      background: #d9d9d9;
      width: 49px;
      height: 24px;
      text-align: center;
      line-height: 24px;
      border-radius: 18px;
      font-size: 14px;
      color: #484848;
      margin-right: 14px;
      margin-top: 5px;
      &.selected {
        background: #484848;
        color: #d9d9d9;
      }
    }
  }
  > .newlabals {
    background: transparent;
    border: none;
    padding: 0 4px;
    border-bottom: 1px solid #666666;
    margin-top: 17px;
    color: #999999;
  }
}
</style>
<template>
  <Layout class-prefix="layout">
    <div class="top">
      <ul class="labals">
        <li>衣</li>
        <li>食</li>
        <li>住</li>
        <li>行</li>
        <li>衣</li>
        <li>食</li>
        <li>住</li>
        <li>行</li>
        <li>衣</li>
        <li>食</li>
        <li>住</li>
      </ul>
      <button class="newlabals">新增标签</button>
    </div>
    <label class="notes">
      <span>备注</span>
      <input placeholder="在这里添加备注" type="text" />
    </label>
    <div class="write">
      <ul class="xuan">
        <li class="selected">支出</li>
        <li>收入</li>
      </ul>
      <input type="text" />
      <div class="numberPad">
        <button>1</button>
        <button>2</button>
        <button>3</button>
        <button>删除</button>
        <button>4</button>
        <button>5</button>
        <button>6</button>
        <button>清空</button>
        <button>7</button>
        <button>8</button>
        <button>9</button>
        <button class="ok">OK</button>
        <button class="zero">0</button>
        <button>.</button>
      </div>
    </div>
  </Layout>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>
<style lang="scss">
  .layout-content {
    border:1px solid red;
    display: flex;
    flex-direction: column;
  }
</style>
<style lang="scss" scoped>
@import "~@/assets/style/helper.scss";
.write {
  margin-top: auto;
  > .xuan {
    display: flex;
    background: #c4c4c4;
    > li {
      flex: 1;
      height: 64px;
      text-align: center;
      line-height: 64px;
      color: #000;
      font-size: 24px;
      &.selected {
        &::after {
          content: "";
          display: block;
          border-bottom: 4px solid #000;
          margin-top: -4px;
        }
      }
    }
  }
  > input {
    width: 100%;
    border: none;
    text-align: right;
    font-size: 36px;
    line-height: 1em;
    padding: 15px 16px 15px 16px;
    font-family: Consolas, monospace;
    box-shadow: inset 0px -2px 3px rgba(0, 0, 0, 0.25);
  }
  > .numberPad {
    @extend %clearFix;
    $color: #f2f2f2;
    width: 100%;
    > button {
      float: left;
      width: 25%;
      height: 64px;
      font-size: 18px;
      color: #000;
      border: none;
      background: transparent;
      &:nth-child(1) {
        background: $color;
      }
      &:nth-child(2),
      &:nth-child(5) {
        background: darken($color, 10%);
      }
      &:nth-child(2),
      &:nth-child(5) {
        background: darken($color, 20%);
      }
      &:nth-child(3),
      &:nth-child(6),
      &:nth-child(9) {
        background: darken($color, 30%);
      }
      &:nth-child(4),
      &:nth-child(7),
      &:nth-child(10),
      &:nth-child(13) {
        background: darken($color, 40%);
      }
      &:nth-child(8),
      &:nth-child(11),
      &:nth-child(14) {
        background: darken($color, 50%);
      }
    }
    > .ok {
      height: 128px;
      line-height: 128px;
      float: right;
      background: darken($color, 60%);
    }
    > .zero {
      width: 50%;
    }
  }
}
.notes {
  display: flex;
  align-items: center;
  > span {
    margin-left: 16px;
  }
  > input {
    flex: 1;
    padding: 20px 15px;
    color: #999999;
    border: none;
    background: transparent;
  }
}
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
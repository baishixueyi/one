<template>
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
</template>

<script>
    export default {
        
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
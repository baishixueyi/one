<template>
    <label class="notes">
      <span>备注</span>
      <input placeholder="在这里添加备注" type="text" />
    </label>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
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
</style>
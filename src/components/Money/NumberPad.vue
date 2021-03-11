<template>
  <div class="write">
    <ul class="xuan">
      <li :class="type === '-' && 'selected'" @click="selectedType('-')">
        支出
      </li>
      <li :class="type === '+' && 'selected'" @click="selectedType('+')">
        收入
      </li>
    </ul>
    <input type="text" :value="output"/>
    <div class="numberPad">
      <button @click="numbers">1</button>
      <button @click="numbers">2</button>
      <button @click="numbers">3</button>
      <button @click="remove">删除</button>
      <button @click="numbers">4</button>
      <button @click="numbers">5</button>
      <button @click="numbers">6</button>
      <button @click="clear">清空</button>
      <button @click="numbers">7</button>
      <button @click="numbers">8</button>
      <button @click="numbers">9</button>
      <button @click="confirm" class="ok">OK</button>
      <button @click="numbers" class="zero">0</button>
      <button @click="numbers">.</button>
    </div>
  </div>
</template>
// TS ->编译 ->js->运行->浏览器
<script>
  import { Component, Prop, Vue } from 'vue-property-decorator';
  @Component
  export default class NmberPad extends Vue {
    @Prop() type
    output = '0'
    //@Prop(Number) xxx:number | undefined;
    //Prop 告诉Vue xxx不是data是prop
    //Number 是告诉Vue xxx运行时是个Number
    //xxx 属性名
    //number | undefined 告诉TS xxx的编译时类型
    selectedType(type) {
      if (type !== "-" && type !== "+") {
        throw new Error("type is nuknown");
      }
      //this.type = type;
      this.$emit('update:type',type)
    }
    numbers(even){
      console.log(even)
      const input = even.target.innerText;
      if(this.output ==='0' && '0123456789'.indexOf(input)>=0){
        this.output = input;
      }else {
        if(this.output.indexOf('.')>=0 && input ==='.'){
          return;
        }else {
          this.output = this.output + input;
        }
        
      }
    }
    remove(){
      this.output = this.output.substr(0,this.output.length-1);
    }
    clear(){
      this.output = '0';
    }
    confirm(){
      const data = [this.type,this.output]
      this.$emit('update:value',data)
      this.$emit('submit',data);
      this.output = '0';
    }
  }
</script>

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
      &:nth-child(10){
        background: darken($color, 40%);
      }
      &:nth-child(8),
      &:nth-child(11){
        background: darken($color, 50%);
      }
      &:nth-child(14) {
        background: darken($color, 55%);
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
      background: darken($color, 45%);
    }
  }
}
</style>
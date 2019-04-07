<template>
  <div id="app">
    <div class="parent-box">
      <h3>我是父元素,$parent,$children方式</h3>
      <p class="content">
        通过$children获得子元素属性{{children1}}
      </p>
      <Children1></Children1>
    </div>

    <div class="parent-box">
      <h3>我是父元素,props方式</h3>
      <p class="content">
        通过$emit触发children改变{{children2}}
      </p>
      <Children2 @changeChild2="changeChild2" :value="children2"></Children2>
    </div>

    <div class="parent-box">
      <h3>我是父元素,总线方式</h3>
      <Children31></Children31>
      <Children32></Children32>
    </div>

    <div class="parent-box">
      <h3>我是父元素A,$attrs,$listeners方式</h3>
      <Children4 :value1="value1" :value2="value2" @clickEvent1="clickEvent1" @clickEvent2="clickEvent2"></Children4>
    </div>

    <div class="parent-box">
      <h3>我是父元素,provide,inject方式</h3>
      <Children5></Children5>
    </div>
  </div>
</template>

<script>
import Children1 from './components/Children1'
import Children2 from './components/Children2'
import Children31 from './components/Children3.1'
import Children32 from './components/Children3.2'
import Children4 from './components/Children4.1'
import Children5 from './components/Children5'

export default {
  name: 'app',
  components: {
    Children1,
    Children2,
    Children31,
    Children32,
    Children4,
    Children5
  },
  data(){
    return {
      parent1:'parent1',
      children1:'',
      children2:'children2',
      value1:'B',
      value2:'C',
      theme:'blue'
    }
  },
  computed:{
  },
  provide(){
    return {
      test:this
    }
  },
  mounted() {
    this.children1 = this.$children[0]._data.value
  },
  methods:{
    changeChild2(val){
      this.children2 = val
    },
    clickEvent1(){
      this.value1 = Math.random()
    },
    clickEvent2(){
      this.value2 = Math.random()
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  .parent-box {
    border: 1px solid deepskyblue;
    padding: 10px;
  }
</style>

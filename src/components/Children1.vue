<template>
    <div class="children-box">
        <h4>我是子元素</h4>
        <input type="text" v-model="parent">
        <p>通过$parent获取父元素的属性 {{parent}}</p>
    </div>
</template>
<script>
    export default {
        data(){
            return {
                value:'children1',
                parent:this.$parent._data.parent1
            }
        },
        mounted() {
        },
        watch:{
            parent(val){
                this.$parent._data.parent1 = val
            }
        }
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>
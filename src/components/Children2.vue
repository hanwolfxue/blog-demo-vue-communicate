<template>
    <div class="children-box">
        <h4>我是子元素</h4>
        <p>value: {{value}}</p>
        <button @click="clickEvent">改值</button>
    </div>
</template>
<script>
    export default {
        props:['value'],
        methods:{
            clickEvent(){
                this.$emit('changeChild2',Math.random())
            }
        }
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>
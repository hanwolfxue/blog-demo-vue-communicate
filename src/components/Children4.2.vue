<template>
    <div class="children-box">
        <h4>我是子元素C</h4>
        <p>{{value2}}</p>
        <button @click="clickEvent">改变value1的值</button>
    </div>
</template>
<script>
    export default {
        name:'Children42',
        inheritAttrs:false,
        props:['value2'],
        data(){
            return {
            }
        },
        mounted() {
        },
        methods:{
            clickEvent(){
                this.$emit('clickEvent2')
            }
        },
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>